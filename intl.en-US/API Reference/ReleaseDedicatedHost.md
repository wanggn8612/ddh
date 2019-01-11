# ReleaseDedicatedHost {#ReleaseDedicatedHost .reference}

To release a Pay-As-You-Go DDH, make sure that no ECS instance is deployed on the DDH.

## Request parameters {#RequestParameter .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set the value to ReleaseDedicatedHost.|
|RegionId|String|Yes|The ID of the region where the DDH is created.For more information, call [DescribeRegions](../../intl.en-US/API Reference/Regions/DescribeRegions.md#) to obtain the latest region list.|
|DedicatedHostId|String|Yes|The ID of the DDH.|

## Response parameters {#ResponseParameter .section}

All are common response parameters. See [Common response parameters](../../intl.en-US/API Reference/Getting started/Common parameters.md#commonResponseParameters).

## Examples {#Samples .section}

**Sample requests** 

```
https://ecs.aliyuncs.com/?Action=ReleaseDedicatedHost
&RegionId=cn-hangzhou
&DedicatedHostId=dh-dedicatedhost1
&<Common request parameters>
```

**Sample responses**

**XML format**

```
<ReleaseDedicatedHostResponse>
  <RequestId>A1B15AC8-E6F6-49A4-8985-8C07104B9199</RequestId>
</ReleaseDedicatedHostResponse>
```

**JSON format**

```
{
    "RequestId":"A1B15AC8-E6F6-49A4-8985-8C07104B9199"
}
```

## Error codes {#ErrorCode .section}

Error codes specific to this interface are as follows. For more information, see [API Error Center](https://error-center.alibabacloud.com/status/product/Ecs).

|Error code|Error message|HTTP status code|Description|
|:---------|:------------|:---------------|:----------|
|InstanceExist|Instance exists on the dedicated host.|400|The error message returned when ECS instances are deployed on the specified DDH. You must release these instances first.|
|OperationDenied.NotAuthorized|End user is not authorized to release the dedicated host.|403|The error message returned when you are not authorized to release the DDH.|
|InvalidDedicatedHostId.NotFound|The specified DedicatedHostId does not exist.|404|The error message returned when the specified DDH ID does not exist.|
|InternalError|The request processing has failed due to some unknown error, exception or failure.|500|The error message returned when an unknown internal error occurs.|

