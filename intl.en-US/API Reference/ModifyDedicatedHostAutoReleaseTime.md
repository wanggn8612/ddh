# ModifyDedicatedHostAutoReleaseTime {#ModifyDedicatedHostAutoReleaseTime .reference}

You can call this operation to set the release time or disable auto-release for a DDH. At the scheduled time, Pay-As-You-Go DDHs will be released. Make sure that you have stopped using these DDHs, and backed up data as needed.

## Request parameters {#RequestParameter .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set the value to ModifyDedicatedHostAutoReleaseTime.|
|DedicatedHostId|String|Yes|The ID of the DDH that you want to automatically release.|
|AutoReleaseTime|String|No|The auto-release time of a DDH. If you do not enter the AutoReleaseTime parameter, auto-release is disabled. The DDH will not be released when the scheduled time is reached.-   The difference between the current system time and the scheduled release time must be no less than half an hour and no more than three years.
-   If the seconds parameter \(`ss`\) is set to a value other than `00`, then `00` is automatically selected.

|

## Response parameters {#ResponseParameter .section}

## Examples {#Samples .section}

**Sample requests** 

```
https://ecs.aliyuncs.com/?Action=ModifyDedicatedHostAutoReleaseTime
&DedicatedHostId=dh-dedicatedhost1
&<Common request parameters>
```

**Sample responses**

**XML format**

```
<ModifyDedicatedHostAutoReleaseTimeResponse>
    <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
</ModifyDedicatedHostAutoReleaseTimeResponse>
```

**JSON format**

```
{ 
    "RequestId": "C0003E8B-B930-4F59-ADC0-0E209A9012A8"
}
```

## Error codes {#ErrorCode .section}

|Error code|Error message|HTTP status code|Description|
|:---------|:------------|:---------------|:----------|
|MissingParameter|DedicatedHostId should not be null.|400|The error message returned when DedicatedHostId is not specified. You must specify this parameter.|
|InvalidAutoReleaseTime.Malformed|The specified parameter autoReleaseTime is not valid.|400|The error message returned when the specified AutoReleaseTime parameter is invalid.|
|UnsupportedParameter|The parameters is unsupported.|400|The error message returned when the specified parameter is not supported.|
|ChargeTypeViolation|The operation is not permitted due to charge type of the dedicated host.|403|The error message returned when the DDH you release is not a Pay-As-You-Go DDH. You can only release Pay-As-You-Go DDHs.|
|NoSuchResource|The specified resource is not found.|404|The error message returned when the specified resource does not exist.|
|InternalError|The request processing has failed due to some unknown error, exception or failure.|500|The error message returned when an unknown internal error occurs.|

