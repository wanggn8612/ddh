# ModifyInstanceDeployment {#ModifyInstanceDeployment .reference}

You can call this operation to change the host of an Elastic Compute Service \(ECS\) instance to another host in the same region.

## Description {#section_i5w_p32_lfb .section}

You can call the ModifyInstanceDeployment operation to complete the following tasks:

-   Change the deployment set of an ECS instance. For example, you can add an ECS instance to a deployment set or change the deployment set of an ECS instance. The DeploymentSetId parameter is required for this task.

    **Note:** You cannot change the deployment set when modifying the Dedicated Host \(DDH\) parameters, including Tenancy, Affinity, and DedicatedHostId.

-   Migrate an ECS instance to a DDH. The following table describes some scenarios.

    |Scenario|Parameter setting|Execution result|
    |:-------|:----------------|:---------------|
    |Migrate an ECS instance from a shared host to a DDH.|DedicatedHostId: Specify the DDH ID.|The ECS instance is migrated to the specified DDH.|
    |Set the following parameters:     -   DedicatedHostId: Leave this parameter empty.
    -   Tenancy: Set this parameter to host.
 |Alibaba Cloud automatically selects a DDH to host the ECS instance.|
    |Migrate an ECS instance between two DDHs.|DedicatedHostId: Specify the DDH ID.|The ECS instance is migrated to the specified DDH.|
    |Set the following parameters:     -   DedicatedHostId: Leave this parameter empty.
    -   Tenancy: Set this parameter to host.
 |Alibaba Cloud automatically selects a DDH to host the ECS instance.|


When migrating an ECS instance to a DDH, note the following information:

-   Ensure that the ECS instance is in the Stopped state before migration. The instance is automatically restarted after migration.
-   You can migrate only VPC-connected ECS instances.
-   The target DDH and the ECS instance to be migrated must have the same billing method.
-   When you migrate an ECS instance from a shared host to a DDH, the billing method of the ECS instance must be pay-as-you-go. You cannot migrate subscription instances or preemptible instances.

## Request parameters {#RequestParameter .section}

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set this parameter to ModifyInstanceDeployment.|
|RegionId|String|Yes|The region ID of the ECS instance.For more information, call [DescribeRegions](../../intl.en-US/API Reference/Regions/DescribeRegions.md#) to obtain the latest region list.|
|InstanceId|String|Yes|The ID of the ECS instance. The instance must be in the `Stopped` or `Running` state.|
|DeploymentSetId|String|No|The ID of the deployment set.|
|DedicatedHostId|String|No|The ID of the DDH. You can call the [DescribeDedicatedHosts](intl.en-US/API Reference/DescribeDedicatedHosts.md#) operation to view the available DDHs.|
|Force|Boolean|No|Specifies whether the host can be changed for the ECS instance. Valid values: -   true: specifies that the host can be changed for the instance. You can also restart a **Running** instance, a **Stopped** subscription instance, or a **Stopped** pay-as-you-go instance that is still billed.
-   false: specifies that the host cannot be changed for the instance. You can only add the instance on the current host to a deployment set. This may cause the ModifyInstanceDeployment operation to fail.

 Default value: `false`.

 |
|Tenancy|String|No|Specifies whether the ECS instance is deployed on a DDH. Valid values: host: specifies that the instance is deployed on a DDH.

 For more information, see the scenario description in [ModifyInstanceDeployment](#table_sas_j9h_0l4).

 |
|Affinity|String|No|Specifies whether the ECS instance is associated with a DDH. Valid values: -   host: specifies that the instance is associated with a DDH. After a stopped instance that is not billed is restarted, it is still hosted on the original DDH.
-   default: specifies that the instance is not associated with a DDH. After a stopped instance that is not billed is restarted, if the original DDH has insufficient resources, the instance can be migrated to another DDH in the automatic deployment resource pool.

 When the instance is migrated from a shared host to a DDH, the default value is `default`.

 |

## Response parameters {#ResponseParameter .section}

All are common response parameters. See [Common response parameters](../../intl.en-US/API Reference/Getting started/Common parameters.md#commonResponseParameters).

## Examples {#section_q0h_l47_qfv .section}

**Sample request** 

``` {#codeblock_j69_zlq_r7q}
https://ecs.aliyuncs.com/?Action=ModifyInstanceDeployment
&RegionId=cn-hangzhou
&DeploymentSetId=ds-bp13v7bjnj9gisnlo1
&<Common request parameters>
```

**Sample success response** 

**XML format**

``` {#codeblock_2zt_6am_mw8}
<ModifyInstanceDeploymentResponse>
    <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
</ModifyInstanceDeploymentResponse>
```

 **JSON format** 

``` {#codeblock_xu1_re8_s4k}
{
    "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## Error codes {#ErrorCode .section}

|Error code|Error message|HTTP status code|Description|
|:---------|:------------|:---------------|:----------|
|DeploymentSet.InvalidId|The specified Deployment Set id doesn't exist.|400|The error message returned because the specified DeploymentSetId parameter does not exist.|
|DeploymentSet.InstanceLimitExceeded|The number of instances on the specified Deployment Set has reached the limit.|403|The error message returned because the number of instances in the specified deployment set has exceeded the upper limit.|
|IncorrectInstanceStatus|The current status of the resource does not support this operation.|403|The error message returned because the operation is not supported while the resource is in the current state.|
|DeploymentSet.ModificationFailed|The modification of deployment set is currently impossible.|403|The error message returned because you cannot change the deployment set.|
|InvalidInstanceId.NotFound|The specified InstanceId does not exist.|404|The error message returned because the specified InstanceId parameter does not exist.|
|InvalidDedicatedHostId.NotFound|The specified DedicatedHostId does not exist.|404|The error message returned because the specified DedicatedHostId parameter does not exist.|
|LackResource|There's no enough resource on the specified dedicated host.|400|The error message returned because the specified DDH is fully loaded.|
|OperationDenied.UnstoppedInstance|Operation denied due to unstopped instancein your request.|400|The error message returned because the ECS instance that you want to migrate is not stopped. Stop the ECS instance before you migrate it to a DDH and try again.|
|InvalidPeriod.ExceededDedidactedHost|Instance expired date can't exceed dedicated host expired date.|400|The error message returned because the expiration time of the subscription ECS instance is later than that of the DDH.|
|InvalidInstanceNetworkType.NotSupport|The specified Instance network type not support.|404|The error message returned because the ECS instance that you want to migrate is not in a VPC. You can migrate only VPC-connected ECS instances.|
|InvalidInstanceChargeType.NotSupport|The Dedicated host not support the specified Instance charge type.|404|The error message returned because the type of the ECS instance that you want to migrate is not supported. When you migrate an ECS instance from a shared host to a DDH, the billing method of the ECS instance must be pay-as-you-go. You cannot migrate subscription instances or preemptible instances.|
|InvalidInstanceType.NotSupport|The Dedicated host not support the specified Instance type|404|The error message returned because the DDH does not support the type of the specified ECS instance.|
|InvalidDedicatedHostStatus.NotSupport|Operation denied due to dedicated host status|400|The error message returned because your account has an overdue payment or the DDH is not available.|
|InternalError|The request processing has failed due to some unknown error,exception or failure.|500|The error message returned because an internal error has occurred.|
|LackResource|There's no enough dedicated host resource.|400|The error message returned because the DDH resources in the automatic deployment resource pool are insufficient.|
|InvalidParameter.Param|Requested param is invalid.|400|The error message returned because the request parameters are invalid.|
|InvalidParam.Tenancy|Instance tenancy is illegal in such case.|400|The error message returned because the specified Tenancy parameter is invalid.|
|InvalidParam.DedicatedHostId|The specified dedicated host id is the same with present host id!|400|The error message returned because the specified DedicatedHostId parameter is the same as the ID of the DDH where the ECS instance is hosted.|
|InvalidDedicatedHostId.NotSupport|Cannot choose instance present host as destination host.|404|The error message returned because you use the DDH where the ECS instance is hosted as the target DDH of the instance. Use another DDH as the target DDH of the instance and try again.|
|InvalidDedicatedHost.NotFound|No available host.|404|The error message returned because no DDH is available.|

