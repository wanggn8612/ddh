# ModifyDedicatedHostAttribute {#ModifyDedicatedHostAttribute .reference}

You can call this operation to modify the information of a DDH, including the name of the DDH, the description of the DDH, and the service unavailability attributes.

## Request parameters {#RequestParameter .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set the value to ModifyDedicatedHostAttribute|
|RegionId|String|Yes|The ID of the region where the DDH is created.For more information, call [DescribeRegions](../../intl.en-US/API Reference/Regions/DescribeRegions.md#) to obtain the latest region list.|
|DedicatedHostId|String|Yes|The ID of the DDH.|
|DedicatedHostName|String|No|The name of the DDH. The name is a string of 2 to 128 characters. It must begin with an English or a Chinese character. It can contain A-Z, a-z, Chinese characters, numbers, periods \(.\), colons \(:\), underscores \(\_\), and hyphens \(-\).|
|Description|String|No|The description of the DDH. It cannot begin with http:// or https://.|
|ActionOnMaintenance| String|No|This value that is used to migrate the instances when a DDH failure occurs or the DDH needs to be repaired. Valid values:-   Migrate: Migrates instances to other physical servers and restarts the instances.

This method is selected when cloud disks are mounted to the DDH.

-   Stop: Stops all instances on the DDH, migrates the instances to another physical server, and restarts the instances if the DDH cannot be repaired.

This method is selected when local disks are mounted to the DDH.


|
|NetworkAttributes.SlbUdpTimeout|Integer|No|The timeout of the UDP session that is established to SLB. Unit: seconds. Value range: \[15,310\]|
|NetworkAttributes.UdpTimeout|Integer|No|The timeout of UDP sessions that are established from users to cloud services on the DDH. Unit: seconds. Value range: \[15,310\]|

## Response parameters {#ResponseParameter .section}

All are common response parameters. See [Common response parameters](../../intl.en-US/API Reference/Getting started/Common parameters.md#commonResponseParameters).

## Samples {#Samples .section}

**Sample requests** 

```
https://ecs.aliyuncs.com/?Action=ModifyDedicatedHostAttribute
&RegionId=cn-hangzhou
&DedicatedHostId=dh-dedicatedhost1
&Description=hello-world
&<Common Request Parameters>
```

**Sample responses**

**XML format**

```
<ModifyDedicatedHostAttributeResponse>
  <RequestId>2A4EA075-CB5B-41B7-B0EB-70D339F64DE7</RequestId>
</ModifyDedicatedHostAttributeResponse>
```

**JSON format**

```
{
    "RequestId":"2A4EA075-CB5B-41B7-B0EB-70D339F64DE7"
}
```

## Error codes {#ErrorCode .section}

|Error code|Error message|HTTP status code|Description|
|:---------|:------------|:---------------|:----------|
|InvalidInstanceName.Malformed|The specified parameter DedicatedHostName is not valid.|400|The error message returned when parameter DedicatedHostName is invalid.|
|InvalidDescription.Malformed|The specified parameter Description is not valid.|400|The error returned when the specified Descrption parameter is invalid.|
|InvalidUser.Unauthorized|The user is not authorized|401|The error message returned when you are not authorized to modify the information about this dedicated host.|
|InvalidDedicatedHostId.NotFound|The specified RegionId does not exist.|404|The error message returned when the specified DDH ID does not exist.|
|InternalError|The request processing has failed due to an unknown error, exception or failure.|500|The error message returned when an unknown internal error occurs.|

