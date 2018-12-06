# AllocateDedicatedHosts {#AllocateDedicatedHosts .reference}

You can call this operation to create one or more Subscription-based DDHs. Alibaba Cloud Dedicated Host \(DDH\) provides dedicated physical servers for each tenant. You can create ECS instances on a DDH and obtain information about the attributes of the physical servers.

## Description {#Details .section}

You can call the [DescribeAvailableResource](intl.en-US/API Reference/Regions/DescribeAvailableResource.md#) operation to view the available resources in the specified region or zone before creating a DDH. Creating a DDH incurs resource consumption fees. Before you create a DDH, make sure that you have read and understood the billing methods for DDH. For more information, see [Pricing overview](../intl.en-US/Pricing/Pricing overview.md#).

-   You can create up to 100 Subscription-based DDHs at a time.

-   After a DDH is created, you can query its status by calling the [RenewDedicatedHosts](intl.en-US/API Reference/RenewDedicatedHosts.md#) operation with the returned DDH ID list as its parameters.

-   When the status of the DDH that you have created is **Available** \(`Available`\), you can start creating ECS instances on the DDH. For the lifecycle of a DDH , see [Life cycle of DDH](../intl.en-US/Product Introduction/Life cycle of DDH.md#) .
-   After you have submitted the DDH creation task, if the corresponding parameters are invalid or no resources are available in the specified region, an error is returned. For more information, see [Error codes](#).

-   After a DDH is created, you can call the [ModifyInstanceDeployment](intl.en-US/API Reference/Deployment sets/ModifyInstanceDeployment.md#) operation to migrate ECS instances from a shared host to the DDH. You can also migrate ECS instances from another DDH to the newly created DDH.


## Request parameters {#RequestParameter .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set the value to AllocateDedicatedHosts|
|RegionId|String|Yes|The ID of the region where the DDH is created.For more information, call [DescribeRegions](../../intl.en-US/API Reference/Regions/DescribeRegions.md#) to obtain the latest region list.|
|DedicatedHostType|String|Yes|DDH types. You can call [DescribeDedicatedHostTypes](intl.en-US/API Reference/DescribeDedicatedHostTypes.md#) to obtain the latest DDH type list.|
|Quantity|Integer|No|The number of DDHs that you want to create this time. Value range: \[1, 100\].Default value: 1.

|
|ZoneId|String|No|The number of the zone where the DDH is created.No default value is available. If you do not specify a zone, the system automatically selects a zone.

|
|DedicatedHostName|String|No|The name of the DDH.The name is a string of 2 to 128 characters. It must begin with an English or a Chinese character. It can contain A-Z, a-z, Chinese characters, numbers, periods \(.\), colons \(:\), underscores \(\_\), and hyphens \(-\).|
|Description| String|No|The description of the DDH.It cannot begin with http:// or https://.|
|ChargeType|String|No|The billing method of the DDH. Valid values:-   PrePaid: Subscription. When you choose the Subscription billing method, make sure that you have a valid payment method. Otherwise, `InvalidPayMethod` is returned.

|
|Period|Integer|No|Set the Subscription period. Unit: Month. Value range: \[1, 9\] | 12 | 24 | 36**Note:** The Period parameter takes effect and is required only when ChargeType is set to PrePaid.

|
|AutoRenew|Boolean|No|Indicates whether a subscription DDH is automatically renewed. Default value: False.**Note:** The AutoRenew parameter takes effect only when ChargeType is set to PrePaid.

|
|AutoRenewPeriod|Integer|Optional|The auto-renewal period. Unit: Month. Valid values: 1 | 2 | 3 | 6 | 12**Note:** The AutoRenewPeriod parameter takes effect and is required only when AutoRenew is set to True.

|
|ActionOnMaintenance|String|No|The method that is used to migrate the instances when a DDH failure occurs or you need to repair the DDH online. Valid valus:-   Migrate: Migrates instances to other physical servers and restart the instances.

This value is automatically selected when cloud disks have been attached to the DDH.

-   Stop: Stops all instances on the DDH, confirms that the DDH cannot be repaired, migrates the instances to another physical server, and restarts the instances.

This value is automatically selected when local disks have been attached to the DDH.


|
|NetworkAttributes.SlbUdpTimeout|Integer|No|The timeout of the UDP session that has been established from the SLB instance. Unit: seconds. Value range: \[15,310\]|
|NetworkAttributes.UdpTimeout|Integer|No|The timeout of UDP sessions that are established from users to cloud services on the DDH. Unit: seconds. Value range: \[15,310\]|
|Tag.n.Key|String|No|Dedicated HostThe key of a tag of which n is from 1 to 20. Once you use this parameter, it cannot be a null string. It can be up to 64 characters in length. It cannot begin with "aliyun", "acs:", "http://", or "https://".|
|Tag.n.Value|String|No|Dedicated HostThe value of a tag of which n is a number from 1 to 20. Once you use this parameter, it can be a null string. It can be up to 128 characters in length. It cannot begin with "aliyun", "acs:", "http://", or "https://".|
|ClientToken|String|No|Guarantees the idempotence of the request.  The value is generated by a client and must be globally unique. Only ASCII characters are allowed. It can contain a maximum of 64 ASCII characters. For more information, see [How to ensure idempotence](../../intl.en-US/API Reference/Appendix/How to ensure idempotence.md#).

|

## Response parameters {#ResponseParameter .section}

|Name|Type|Discription|
|:---|:---|:----------|
|DedicatedHostIdSets|Array of DedicatedHostId|A list of DDH IDs \(DedicatedHostId\).|

## Samples {#Samples .section}

**Sample requests** 

```
https://ecs.aliyuncs.com/?Action=AllocateDedicatedHosts
&RegionId=cn-hangzhou
&DedicatedHostType=ddh.sn1ne
&Quantity=2
&<Common Request Parameters>
```

**Sample responses**

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

|Error code|Error message|HTTP status code |Description|
|:---------|:------------|:----------------|:----------|
|Account.Arrearage|Your account has an outstanding payment.|400|The error message returned when your account has an overdue payment.|
|InvalidChargeType.ValueNotSupported|ChargeType is not valid.|400|The error message returned when the ChargeType parameter is invalid.|
|InvalidDedicatedHostName.Malformed|The specified parameter HostName is not valid.|400|The error message returned when the specified DedicatedHostName is invalid.|
|InvalidDescription.Malformed|The specified parameter Description is not valid.|400|The error message returned when the specified Description is invalid.|
|MissingParamter|The specified parameter Period can’t be null|400|The error message returned when the Period parameter is not set. The Period parameter is required when ChargeType is set to Prepaid.|
|OperationDenied|Sales of this resource are temporarily suspended in the specified region; please try again later.|400|The error message returned when DDH is not available in the specified region.|
|OperationDenied.NoStock|Sales of this resource are temporarily suspended in the specified region; please try again later.|400|The error message returned when no DDH resources are available. Select another resource type or zone.|
|QuotaExceed.AfterpayDedicatedHost|Living afterpay dedicated host quota exceeded.|400|The error message returned when the number of DDHs that you can create has exceeded the maximum number.|
|Zone.NotOnSale|The specified zone is not available for purchase.|400|The error message returned when you cannot create a DDH in the specified zone.|
|Forbbiden|User not authorized to operate on the specified resource.|403|The error message returned when you are not authorized to create a DDH.|
|RegionUnauthorized|User has no authority to create instance in the specified region.|403|The error message returned when you are not authorized to create a DDH in the specified region.|
|Zone.NotOpen|The specified zone is not granted to you to buy resources yet.|403|The error message returned when you are not authorized to create a DDH in the specified zone.|
|InvalidDedicatedHostChargeType.NotFound|The DedicatedHostChargeType does not exist in our records.|404|The error message returned when the specified ChargeType does not exist.|

