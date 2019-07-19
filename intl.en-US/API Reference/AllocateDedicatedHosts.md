# AllocateDedicatedHosts {#AllocateDedicatedHosts .reference}

You can call this operation to create one or more subscription Dedicated Hosts \(DDHs\). Alibaba Cloud DDH provides dedicated physical servers for each tenant. You can create Elastic Compute Service \(ECS\) instances on a DDH and obtain the attributes of the physical servers.

## Description {#Details .section}

Before creating a DDH, you can call the [DescribeAvailableResource](intl.en-US/API Reference/Regions/DescribeAvailableResource.md#) operation to view the available resources in the specified region or zone.

Creating a DDH incurs resource consumption fees. Before you create a DDH, we recommend that you read and understand the billing methods for DDHs. For more information, see [Pricing overview](../intl.en-US/Pricing/Pricing overview.md#).

-   You can create a maximum of 100 subscription DDHs at a time.
-   After one or more DDHs are created, a DDH ID list is returned. You can call the [DescribeDedicatedHosts](intl.en-US/API Reference/DescribeDedicatedHosts.md#) operation to query the status of DDHs in the DDH ID list.
-   When the status of a created DDH is ****`Available`, you can start to create ECS instances on the DDH. For more information about the lifecycle of a DDH, see [Lifecycle](../intl.en-US/Product Introduction/Life cycle of DDH.md#).
-   After you submit a DDH creation task, an error may occur if the parameters are invalid or DDH resources are insufficient. For more information, see [Error codes](#).
-   After a DDH is created, you can call the [ModifyInstanceDeployment](intl.en-US/API Reference/Deployment sets/ModifyInstanceDeployment.md#) operation to migrate ECS instances from a shared host to the DDH. You can also migrate ECS instances from another DDH to the created DDH.

## Request parameters {#RequestParameter .section}

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set this parameter to AllocateDedicatedHosts.|
|RegionId|String|Yes|The region ID of the DDH.For more information, call [DescribeRegions](../../intl.en-US/API Reference/Regions/DescribeRegions.md#) to obtain the latest region list.|
|DedicatedHostType|String|Yes|The type of the DDH. You can call the [DescribeDedicatedHostTypes](intl.en-US/API Reference/DescribeDedicatedHostTypes.md#) operation to obtain the latest DDH type list.|
|Quantity|Integer|No|The number of DDHs that you want to create this time. Valid values: \[1, 100\]. Default value: 1.

 |
|ZoneId|String|No|The zone ID of the DDH. No default value is available. If you do not specify a zone, the system automatically selects a zone.

 |
|DedicatedHostName|String|No|The name of the DDH.The name is a string of 2 to 128 characters. It must begin with an English or a Chinese character. It can contain A-Z, a-z, Chinese characters, numbers, periods \(.\), colons \(:\), underscores \(\_\), and hyphens \(-\).|
|Description|String|No|The description of the DDH.It cannot begin with http:// or https://.|
|ChargeType|String|No|The billing method of the DDH. Valid values: PrePaid, indicating subscription.

 **Note:** If you set this parameter to PrePaid, ensure that you have a valid payment method. Otherwise, `InvalidPayMethod` is returned.

 |
|Period|Integer|No|The subscription period of the DDH. Unit: months. Valid values: \[1, 9\], 12, 24, and 36. **Note:** The Period parameter takes effect and is required only when the ChargeType parameter is set to PrePaid.

 |
|AutoRenew|Boolean|No|Specifies whether the subscription DDH is automatically renewed. Default value: `False`. **Note:** The AutoRenew parameter takes effect only when the ChargeType parameter is set to PrePaid.

 |
|AutoRenewPeriod|Integer|No|The auto-renewal period of the DDH. Unit: months. Valid values: 1, 2, 3, 6, and 12. **Note:** The AutoRenewPeriod parameter takes effect and is required only when the AutoRenew parameter is set to True.

 |
|ActionOnMaintenance|String|No|The method used to migrate the instances on the DDH when the DDH fails or needs to be repaired online. Valid values: -   Migrate: specifies that the instances are migrated to another physical server and restarted.

Default value: `Migrate` \(when a cloud disk is attached to the DDH\).

-   Stop: specifies that all the instances on the DDH are stopped. If the DDH cannot be repaired, the instances are migrated to another physical server and restarted.

Default value: `Stop` \(when a local disk is attached to the DDH\).


 |
|NetworkAttributes.SlbUdpTimeout|Integer|No|The timeout period of UDP sessions that are established with Server Load Balancer \(SLB\). Unit: seconds. Valid values: \[15, 310\].|
|NetworkAttributes.UdpTimeout|Integer|No|The timeout period of UDP sessions that are established between users and cloud services running on the DDH. Unit: seconds. Valid values: \[15, 310\].|
|Tag.n.Key|String|No|DDHThe key of a tag of which n is from 1 to 20. Once you use this parameter, it cannot be a null string. It can be up to 64 characters in length. It cannot begin with "aliyun", "acs:", "http://", or "https://".|
|Tag.n.Value|String|No|DDHThe value of a tag of which n is a number from 1 to 20. Once you use this parameter, it can be a null string. It can be up to 128 characters in length. It cannot begin with "aliyun", "acs:", "http://", or "https://".|
|ClientToken|String|No| Guarantees the idempotence of the request.  The value is generated by a client and must be globally unique. Only ASCII characters are allowed. It can contain a maximum of 64 ASCII characters. For more information, see [How to ensure idempotence](../../intl.en-US/API Reference/Appendix/How to ensure idempotence.md#).

 |
|AutoReleaseTime|String|No|The automatic release time of the DDH. Format: `yyyy-MM-ddTHH:mm:ssZ`. **Note:** 

-   Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.
-   If the value of the seconds place is not 00, it is automatically set to 00.
-   The automatic release time must be at least 30 minutes and at most three years later than the current time.

 |
|AutoPlacement|String|No|Specifies whether the DDH is added to the automatic deployment resource pool. If you create an instance on a DDH without specifying the DedicatedHostId parameter, Alibaba Cloud automatically selects a DDH from the resource pool to host the instance. Valid values: -   `on`: adds the DDH to the automatic deployment resource pool.
-   `off`: does not add the DDH to the automatic deployment resource pool.

 Default value: `on`.

**Note:** When you create a DDH:

-   If you do not set this parameter, the DDH is added to the automatic deployment resource pool.
-   If you do not want to add the DDH to the automatic deployment resource pool, set this parameter to `off`.

 |

## Response parameters {#ResponseParameter .section}

|Parameter|Type|Description|
|:--------|:---|:----------|
|DedicatedHostIdSets|Array of DedicatedHostId|The list of DDH IDs \(DedicatedHostId\).|

## Examples {#Samples .section}

 **Sample request** 

```
https://ecs.aliyuncs.com/?Action=AllocateDedicatedHosts
&RegionId=cn-hangzhou
&DedicatedHostType=ddh.sn1ne
&Quantity=2
&<Common request parameters>
```

 **Sample success response** 

**XML format**

```
<AllocateDedicatedHostsResponse>
  <RequestId>192C4203-ED9E-4BCD-847D-482995C01728</RequestId>
  <DedicatedHostIdSets>
    <DedicatedHostId>dh-dedicatedhost1</DedicatedHostId>
    <DedicatedHostId>dh-dedicatedhost2</DedicatedHostId>
  </DedicatedHostIdSets>
</AllocateDedicatedHostsResponse>
```

 **JSON format** 

```
{
    "RequestId":"E2A664A6-2933-4C64-88AE-5033D003EADF",
    "DedicatedHostIdSets":{
        "DedicatedHostId":[
            "dh-dedicatedhost1",
            "dh-dedicatedhost2"
        ]
    }
}
```

## Error codes {#ErrorCode .section}

|Error code|Error message|HTTP status code|Description|
|:---------|:------------|:---------------|:----------|
|Account.Arrearage|Your account has an outstanding payment.|400|The error message returned because your account has an overdue payment.|
|InvalidChargeType.ValueNotSupported|ChargeType is not valid.|400|The error message returned because the specified ChargeType parameter is invalid.|
|InvalidDedicatedHostName.Malformed|The specified parameter DedicatedHostName is not valid.|400|The error message returned because the specified DedicatedHostName parameter is invalid.|
|InvalidDescription.Malformed|The specified parameter Description is not valid.|400|The error message returned because the specified Description parameter is invalid.|
|MissingParamter|The specified parameter Period can’t be null|400|The error message returned because the Period parameter is not set. This parameter is required when the ChargeType parameter is set to PrePaid.|
|OperationDenied|Sales of this resource are temporarily suspended in the specified region; please try again later.|400|The error message returned because DDHs are not available in the specified region.|
|OperationDenied.NoStock|Sales of this resource are temporarily suspended in the specified region; please try again later.|400|The error message returned because DDH resources are insufficient. Select another resource type or zone.|
|QuotaExceed.AfterpayDedicatedHost|Living afterpay dedicated host quota exceeded.|400|The error message returned because the number of DDHs that you create has exceeded the quota.|
|Zone.NotOnSale|The specified zone is not available for purchase.|400|The error message returned because you cannot create a DDH in the specified zone.|
|Forbbiden|User not authorized to operate on the specified resource.|403|The error message returned because you are not authorized to create a DDH.|
|RegionUnauthorized|User has no authority to create instance in the specified region.|403|The error message returned because you are not authorized to create a DDH in the specified region.|
|Zone.NotOpen|The specified zone is not granted to you to buy resources yet.|403|The error message returned because you are not authorized to create a DDH in the specified zone.|
|InvalidDedicatedHostChargeType.NotFound|The DedicatedHostChargeType does not exist in our records.|404|The error message returned because the specified ChargeType parameter does not exist.|

