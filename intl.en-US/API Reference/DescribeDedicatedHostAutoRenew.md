# DescribeDedicatedHostAutoRenew {#DescribeDedicatedHostAutoRenew .reference}

You can call this operation to query the renewal status of one or more Subscription-based DDHs.

## Request parameters {#RequestParameter .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set the value to DescribeDedicatedHostAutoRenew|
|RegionId|String|Yes|The ID of the region where the DDH is created.|
|DedicatedHostIds|String|Yes|The list of DDH IDs. You can enter up to 100 DDH IDs in the list. Separate the IDs by commas \(`,`\).|

## Response parameters {#ResponseParameter .section}

|Name|Type|Required|
|:---|:---|:-------|
|DedicatedHostId|String|The ID of the DDH.|
|Duration|Integer|The duration of auto-renewal.|
|AutoRenewEnabled|Boolean|Indicates whether auto-renewal is enabled.|
|PeriodUnit|String|The unit of renewal duration. Possible values: Week | Month|
|RenewalStatus|String|Indicates whether a Subscription-based DDH has enabled automatic renewal. Possible values:-   AutoRenewal: Auto renewal is enabled.
-   Normal: To be renewed.
-   NotRenewal: Auto renewal is disabled. No notifications. You will receive notifications for renewal three days before the expiration time of a DDH subscription. You can set the DDH that is not set to be renewed to Normal and manually renew it \([RenewDedicatedHosts](intl.en-US/API Reference/RenewDedicatedHosts.md#)\), or set the DDH to auto-renewal \(AutoRenewal\).

|

## Samples {#Samples .section}

**Sample requests** 

```
https://ecs.aliyuncs.com/?Action=DescribeDedicatedHostAutoRenew
&RegionId=cn-hangzhou
&DedicatedHostIds=dh-dedicatedhost1,dh-dedicatedhost2
&<Common Request Parameters>
```

**Sample responses**

**XML format**

```
<DescribeDedicatedHostAutoRenewResponse>
    <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
    <DedicatedHostRenewAttributes>
        <DedicatedHostRenewAttribute>
            <DedicatedHostId>dh-dedicatedhost1</DedicatedHostId>
            <Duration>0</Duration>
            <AutoRenewEnalbed>false</AutoRenewEnalbed>
            <PeriodUnit>Month</PeriodUnit>
            <RenewalStatus>Normal</RenewalStatus>
        </DedicatedHostRenewAttribute>
         <DedicatedHostRenewAttribute>
            <DedicatedHostId>dh-dedicatedhost2</DedicatedHostId>
            <Duration>1</Duration>
            <PeriodUnit>Month</PeriodUnit>
            <AutoRenewEnalbed>true</AutoRenewEnalbed>
            <RenewalStatus>AutoRenewal</RenewalStatus>
        </DedicatedHostRenewAttribute>
    </DedicatedHostRenewAttributes>
</DescribeDedicatedHostAutoRenewResponse>
```

**JSON format**

```
{
    "DedicatedHostIdRenewAttributes": {
        "DedicatedHostIdRenewAttribute": [
            {
                "Duration": 0,
                "DedicatedHostId": "dh-dedicatedhost1",
                "AutoRenewEnabled": false,
                "RenewalStatus": "Normal",
                "PeriodUnit": "Month"
            },
            {
                "Duration": 1,
                "DedicatedHostId": "dh-dedicatedhost2",
                "AutoRenewEnabled": true,
                "RenewalStatus": "AutoRenewal",
                "PeriodUnit": "Month"
            }
        ]
    },
    "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## Error codes {#ErrorCode .section}

|Error code|Error message|HTTP status code |Description|
|:---------|:------------|:----------------|:----------|
|MissingParameter.DedicatedHostId|DedicatedHostId should not be null.|403|The error message returned when the value of DedicatedHostIds is empty. You must enter a value.|
|InvalidParameter.ToManyDedicatedHostIds|DedicatedHostId should be less than 100.|403|The error message returned when the number of DDH IDs is invalid. You can specify up to 100 DDH IDs at a time.|
|InvalidParameter.InvalidDedicatedHostId|The specified dedicatedHostId is not valid|403|The error message returned when the DedicatedHostIds parameter contains an invalid DDH ID.|

