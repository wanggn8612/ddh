# ModifyInstanceDeployment {#ModifyInstanceDeployment .reference}

You can call this operation to migrate an ECS instance to a DDH in the same region.

## Description {#section_i5w_p32_lfb .section}

You can call the ModifyInstanceDeployment operation to complete the following tasks:

-   Add an instance to a deployment set or migrate an instance to another deployment set from the current deployment set. The DeploymentSetId parameter is required for this task.

-   You can migrate ECS instances from a shared host to the specified DDH, or migrate instances between two DDHs to reallocate your resources. The DedicatedHostId parameter is required for this task.


Note the following when migrating ECS instances to a DDH:

-   Make sure that the instance is in the Stopped status before migration. The instance automatically restarts after migration.

-   You can only migrate VPC-connected ECS instances.

-   The billing methods of the target DDH and the ECS instances that you want to migrate must be the same.

-   The billing method of the ECS instance that you migrate to a DDH from a shared host is Pay-As-You-Go only. You cannot migrate Subscription-based instances or preemptible instances.


## Request parameters {#RequestParameter .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set the value to ModifyInstanceDeployment|
|RegionId|String|Yes|The ID of the region where the instance and the host are both created.For more information, call [DescribeRegions](../../intl.en-US/API Reference/Regions/DescribeRegions.md#) to obtain the latest region list.|
|InstanceId|String|Yes|The ID of the instance. The instance must be in the `Stopped` or `Running` status.|
|DeploymentSetId|String|No|The ID of the deployment set.|
|DedicatedHostId|String|No|The ID of the DDH. You can call the [DescribeDedicatedHosts](intl.en-US/API Reference/DescribeDedicatedHosts.md#) operation to query available DDHs.|
|Force|Boolean|No|Indicates whether changing host for instances is supported.-   true: Allows you to change the host for an instance, and restart a **running** instance, a **stopped** Subscription-based instance, or a **stopped** Pay-As-You-Go instance that is still billed.
-   false \(default value\): You are not allowed to change the host for an instance. You can create a deployment set on the current DDH. This may cause the ModifyInstanceDeployment action to fail.

|

## Response parameters {#ResponseParameter .section}

All are common response parameters. See [Common response parameters](../../intl.en-US/API Reference/Getting started/Common parameters.md#commonResponseParameters).

## Samples { .section}

**Sample requests** 

```
https://ecs.aliyuncs.com/?Action=ModifyInstanceDeployment
&RegionId=cn-hangzhou
&DeploymentSetId=ds-bp13v7bjnj9gisnlo1
&<Common Request Parameters>
```

**Sample responses**

**XML format**

```
<ModifyInstanceDeploymentResponse>
	<RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
</ModifyInstanceDeploymentResponse>
```

**JSON format**

```
{
	"RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## Error codes {#ErrorCode .section}

|Error code|Error message|HTTP status code|Description|
|:---------|:------------|:---------------|:----------|
|DeploymentSet.InvalidId|The specified Deployment Set id doesn't exist.|400|The error message returned when the specified DeploymentSetId parameter does not exist.|
|DeploymentSet.InstanceLimitExceeded|The number of instances on the specified Deployment Set has reached the limit.|403|The error message returned when the number of instances in a deployment set has exceeded the maximum number.|
|IncorrectInstanceStatus|The current status of the resource does not support this operation.|403|The error message returned when the current status of the resource does not support this operation.|
|DeploymentSet.ModificationFailed|The modification of deployment set is currently impossible.|403|The error message returned when you cannot modify the deployment set.|
|InvalidInstanceId.NotFound|The specified InstanceId does not exist.|404|The error message returned when the specified instance ID does not exist.|
|InvalidDedicatedHostId.NotFound|The specified RegionId does not exist.|404|The error message returned when the specified DDH ID does not exist.|
|LackResource|There's no enough resource on the specified dedicated host.|400|The error message returned when the specified DDH is fully loaded.|
|OperationDenied.UnstoppedInstance|Operation denied due to unstopped instancein your request.|400|The error message returned when the ECS instance that you want to migrate to another DDH is not stopped. The ECS instance must be stopped before you migrate it to another DDH.|
|InvalidPeriod.ExceededDedidactedHost|Instance expired date can't exceed dedicated host expired date.|400|The error message returned when the expiration time of the Subscription ECS instance is later than that of the DDH. The expiration time of the subscription ECS instance cannot be later than that of the DDH.|
|InvalidInstanceNetworkType.NotSupport|The specified Instance network type not support.|404|The error message returned when you migrate an instance that is not in a VPC network. You can only migrate VPC-connected ECS instances.|
|InvalidInstanceChargeType.NotSupport|The Dedicated host not support the specified Instance charge type.|404|The error message returned when the type of the instance that you want to migrate is not supported. The billing method of the ECS instance that you migrate to a DDH from a shared host is Pay-As-You-Go only. You cannot migrate Subscription-based instances or preemptible instances.|
|InvalidInstanceType.NotSupport|The Dedicated host not support the specified Instance type|404|The error message returned when the DDH does not support the target ECS instance type.|
|InvalidDedicatedHostStatus.NotSupport|Operation denied due to dedicated host status|400|The error message returned when you have an overdue payment or the DDH is not available.|
|InternalError|The request processing has failed due to some unknown error, exception or failure.|500|The error message returned when an unknown internal error occurs.|

