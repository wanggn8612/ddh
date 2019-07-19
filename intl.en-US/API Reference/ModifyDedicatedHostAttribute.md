# ModifyDedicatedHostAttribute {#ModifyDedicatedHostAttribute .reference}

You can call this operation to modify the information about a Dedicated Host \(DDH\), including the name, description, and service unavailability attributes of the DDH.

## Request parameters {#RequestParameter .section}

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set this parameter to ModifyDedicatedHostAttribute.|
|RegionId|String|Yes|The region ID of the DDH.For more information, call [DescribeRegions](../../intl.en-US/API Reference/Regions/DescribeRegions.md#) to obtain the latest region list.|
|DedicatedHostId|String|Yes|The ID of the DDH.|
|DedicatedHostName|String|No|The name of the DDH.The name is a string of 2 to 128 characters. It must begin with an English or a Chinese character. It can contain A-Z, a-z, Chinese characters, numbers, periods \(.\), colons \(:\), underscores \(\_\), and hyphens \(-\).|
|Description|String|No|The description of the DDH.It cannot begin with http:// or https://.|
|ActionOnMaintenance|String|No|The method used to migrate the instances on the DDH when the DDH fails or needs to be repaired online. Valid values: -   Migrate: specifies that the instances are migrated to another physical server and restarted.
-   Stop: specifies that all the instances on the DDH are stopped. If the DDH cannot be repaired, the instances are migrated to another physical server and restarted.

 When a cloud disk is attached to the DDH, the default value is Migrate.

 When a local disk is attached to the DDH, the default value is Stop.

 |
|NetworkAttributes.SlbUdpTimeout|Integer|No|The timeout period of UDP sessions that are established with Server Load Balancer \(SLB\). Unit: seconds. Valid values: \[15, 310\].|
|NetworkAttributes.UdpTimeout|Integer|No|The timeout period of UDP sessions that are established between users and cloud services running on the DDH. Unit: seconds. Valid values: \[15, 310\].|
|AutoPlacement|String|No|Specifies whether the DDH is added to the automatic deployment resource pool. If you create an instance on a DDH without specifying the DedicatedHostId parameter, Alibaba Cloud automatically selects a DDH from the resource pool to host the instance. Valid values: -   on: adds the DDH to the automatic deployment resource pool.
-   off: does not add the DDH to the automatic deployment resource pool.

 |

## Response parameters {#ResponseParameter .section}

All are common response parameters. See [Common response parameters](../../intl.en-US/API Reference/Getting started/Common parameters.md#commonResponseParameters).

## Examples {#Samples .section}

 **Sample request** 

```
https://ecs.aliyuncs.com/?Action=ModifyDedicatedHostAttribute
&RegionId=cn-hangzhou
&DedicatedHostId=dh-dedicatedhost1
&Description=hello-world
&<Common request parameters>
```

 **Sample success response** 

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
|InvalidInstanceName.Malformed|The specified parameter DedicatedHostName is not valid.|400|The error message returned because the specified DedicatedHostName parameter is invalid.|
|InvalidDescription.Malformed|The specified parameter Description is not valid.|400|The error message returned because the specified Description parameter is invalid.|
|InvalidUser.Unauthorized|The user is not authorized|401|The error message returned because you are not authorized to modify the information about this DDH.|
|InvalidDedicatedHostId.NotFound|The specified DedicatedHostId does not exist.|404|The error message returned because the specified DedicatedHostId parameter does not exist.|
|InternalError|The request processing has failed due to some unknown error,exception or failure.|500|The error message returned because an internal error has occurred.|

