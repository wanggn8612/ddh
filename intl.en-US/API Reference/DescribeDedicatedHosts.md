# DescribeDedicatedHosts {#DescribeDedicatedHosts .reference}

You can call this operation to query details about one or more DDHs, including physical performance specifications, virtual machine code, service status, and list of instances that you have created.

## Request parameters {#RequestParameter .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set the value to DescribeDedicatedHosts|
|RegionId|String|Yes|The ID of the region where the DDH is created.For more information, call [DescribeRegions](../../intl.en-US/API Reference/Regions/DescribeRegions.md#) to obtain the latest region list.|
|ZoneId|String|No|The ID of the zone.|
|DedicatedHostIds|Array|No|The list of DDH IDs. A list contains up to 100 DDH IDs. Multiple DDH IDs are displayed as JSON arrays, such as \[“dh- xxxxxxxxx”, “dh- yyyyyyyyy”, … “dh- zzzzzzzzz”\]. IDs are separated by commas \(`,`\).|
|DedicatedHostName|String|No|The name of the DDH.|
|DedicatedHostType|String|No|The type of the DDH.|
|Status|String|No|The service status of the DDH. Valid values:-   Available \(default value\): The DDH is available. You can use the DDH.
-   under-assessment: The DDH has potential failures. Failures may occur when you use the DDH.
-   permanent-failure: The DDH has permanent failures. You cannot use the DDH.

|
|Tag.n.Key| String|No|Dedicated HostThe key of a tag of which n is from 1 to 20. Once you use this parameter, it cannot be a null string. It can be up to 64 characters in length. It cannot begin with "aliyun", "acs:", "http://", or "https://".|
|Tag.n.Value| String|No|Dedicated HostThe value of a tag of which n is a number from 1 to 20. Once you use this parameter, it can be a null string. It can be up to 128 characters in length. It cannot begin with "aliyun", "acs:", "http://", or "https://".|
|PageNumber|Integer|Optional|The number of pages that contain response information.Default value: 1.

|
|PageSize|Integer|No|The number of rows per page that the response content contains. Maximum value: 100 Default value: 10

|

## Response parameters {#ResponseParameter .section}

|Name|Type|Required|
|:---|:---|:-------|
|TotalCount|Integer|The total number of DDHs.|
|PageNumber|Integer|The number of pages contained in the DDH list.|
|PageSize|Integer|The number of rows per page contained in the response results.|
|DedicatedHosts|Array of [DedicatedHostAttributesType](#)|The collection of DDH details.|

**DedicatedHostAttributesType**

|Name|Type|Description|
|:---|:---|:----------|
|DedicatedHostId|String|The ID of the DDH.|
|MachineId|String|The virtual machine code of the DDH.|
|DedicatedHostName|String|The name of the DDH.|
|DedicatedHostType|String|The type of the DDH.|
|Description|String|The description of the DDH.|
|RegionId|String|The ID of the region.|
|ZoneId|String|The ID of the zone.|
|Sockets|Integer|The number of physical CPUs.|
|Cores.|Integer|The number of cores in a CPU.|
|SupportedInstanceTypeFamilies|Array of [SupportedInstanceTypeFamilySetType](#)|The ECS instance type family supported by a DDH.|
|Capacity|Array of [DedicatedHostCapacity](#)|The collection of DDH performance specifications.|
|Instances|Array of [HostInstance](#)|The collection of details about ECS instances that you have created on a DDH.|
|Status |String|The service status of the DDH. Possible values: Available | Under-Assessment | Permanent-Failure|
|CreationTime|String|The time of creation.The time format follows the [ISO8601](../../intl.en-US/API Reference/Appendix/ISO 8601 Time Format.md#) standard, and the UTC time is used. The format is yyyy-MM-ddTHH:mm:ssZ.|
|ChargeType|String|The billing method of the DDH.|
|Salecycle|String|The billing cycle of a Subscription-based DDH.|
|ExpiredTime|String|The expiration time of a Subscription-based DDH.The time format follows the [ISO8601](../../intl.en-US/API Reference/Appendix/ISO 8601 Time Format.md#) standard, and the UTC time is used. The format is yyyy-MM-ddTHH:mm:ssZ.|
|OperationLocks|Array of [OperationLocksType]()|The cause of locked DDH resources.|

**DedicatedHostCapacity**

|Name|Type|Required|
|:---|:---|:-------|
|TotalVcpus|Integer|The total number of cores in the virtual CPU.|
|AvailableVcpus|Integer|The remaining number of cores in the virtual CPU.|
|TotalMemory|Float|The total capacity of the memory. Unit: GiB.|
|AvailablevMemory|Float|The remaining capacity of the memory. Unit: GiB.|
|TotalDisk|Integer|The total capacity of the local disk. Unit: GiB.|
|AvailableDisk|Integer|The remaining capacity of the local disk. Unit: GiB.|
|LocalStorageCategory|String|The type of the local disk.|

**Hostinstance**

|Name|Type|Required|
|:---|:---|:-------|
|InstanceId|String|The ID of the ECS instance that you have created on a DDH.|
|InstanceType|String|The type of the ECS instance that you have created on a DDH.|

**SupportedInstanceTypeFamilySetType**

|Name|Type|Description|
|:---|:---|:----------|
|SupportedInstanceTypeFamily|String|The ECS instance type family supported by a DDH.|

**OperationLocksType**

|Name|Type|Description|
|:---|:---|:----------|
|LockReason|Array of [LockReasonType]()|The reason that the resource is locked.|

**LockReasonType**

|Name|Type|Description|
|:---|:---|:----------|
|LockReason|String|The type of reason. Possible values:financial: You have an overdue payment.

|

## Samples {#Samples .section}

**Sample requests**

```
https://ecs.aliyuncs.com/?Action=DescribeDedicatedHosts
&RegionId=cn-hangzhou
&<Common Request Parameters>
```

**Sample responses**

**XML format**

```
<DescribeDedicatedHostsResponse>
  <PageNumber>1</PageNumber>
  <DedicatedHosts>
    <DedicatedHost>
      <DedicatedHostId>dh-2ze3lmtckdjw1pt8nr82</DedicatedHostId>
      <ChargeType>PostPaid</ChargeType>
      <Description/>
      <ResourceGroupId/>
      <SupportedInstanceTypeFamilies>
        <SupportedInstanceTypeFamily>ecs.se1ne</SupportedInstanceTypeFamily>
      </SupportedInstanceTypeFamilies>
      <Instances/>
      <Cores>32</calCores>
      <ZoneId>cn-beijing-c</ZoneId>
      <CreationTime>2018-08-13T07:59Z</CreationTime>
      <Sockets>2</Sockets>
      <Status>Available</Status>
      <DedicatedHostType>ddh.se1ne</DedicatedHostType>
      <RegionId>cn-beijing</RegionId>
      <DedicatedHostName>dhZ2ze3lmtckdjw1pt8nr82Z</DedicatedHostName>
      <SaleCycle/>
      <AutoReleaseTime/>
      <Capacity>
        <AvailableVcpus>56</AvailableVcpus>
        <TotalMemory>448.0</TotalMemory>
        <TotalVcpus>56</TotalVcpus>
        <AvailableLocalStorage>0</AvailableLocalStorage>
        <TotalLocalStorage>0</TotalLocalStorage>
        <LocalStorageCategory/>
        <AvailableMemory>448.0</AvailableMemory>
      </Capacity>
      <OperationLocks/>
      <MachineId>d7a1bdde71d7429097c36e44a0d1bbdb</MachineId>
      <ExpireTime>2999-09-08T16:00:00Z</ExpireTime>
    </DedicatedHost>
    <DedicatedHost>
      <DedicatedHostId>dh-2ze3lmtckdjw1pt8nr83</DedicatedHostId>
      <ChargeType>PostPaid</ChargeType>
      <Description/>
      <ResourceGroupId/>
      <SupportedInstanceTypeFamilies>
        <SupportedInstanceTypeFamily>ecs.se1ne</SupportedInstanceTypeFamily>
      </SupportedInstanceTypeFamilies>
      <Instances/>
      <Cores>32</Cores>
      <ZoneId>cn-beijing-c</ZoneId>
      <CreationTime>2018-08-13T07:59Z</CreationTime>
      <Sockets>2</Sockets>
      <Status>Available</Status>
      <DedicatedHostType>ddh.se1ne</DedicatedHostType>
      <RegionId>cn-beijing</RegionId>
      <DedicatedHostName>dhZ2ze3lmtckdjw1pt8nr83Z</DedicatedHostName>
      <SaleCycle/>
      <AutoReleaseTime/>
      <Capacity>
        <AvailableVcpus>56</AvailableVcpus>
        <TotalMemory>448.0</TotalMemory>
        <TotalVcpus>56</TotalVcpus>
        <AvailableLocalStorage>0</AvailableLocalStorage>
        <TotalLocalStorage>0</TotalLocalStorage>
        <LocalStorageCategory/>
        <AvailableMemory>448.0</AvailableMemory>
      </Capacity>
      <OperationLocks/>
      <MachineId>f9b97a46c05b38c8c9cfe2b120f26ca6</MachineId>
      <ExpireTime>2999-09-08T16:00:00Z</ExpireTime>
    </DedicatedHost>
  </DedicatedHosts>
  <TotalCount>2</TotalCount>
  <PageSize>10</PageSize>
  <RequestId>C9E9EA51-6B74-409E-BA40-107126A200D4</RequestId>
</DescribeDedicatedHostsResponse>
```

**JSON format**

```
{
    "PageNumber":1,
    "DedicatedHosts":{
        "DedicatedHost":[
            {
                "DedicatedHostId":"dh-dedicatedhost1",
                "ChargeType": "PostPaid",
                "Description": "",
                "ResourceGroupId":"",
                "SupportInstanceTypeFamilies":{
                    "SupportInstanceTypeFamily":[
                        "ecs.se1ne",
                    ]
                },
                "Instances": {
                    "Instance": [

                    ]
                },
                "Cores":32,
                "ZoneId":"cn-beijing-c"
                "CreationTime":"2018-08-13T07:59Z",
                "Sockets":2,
                "Status": "Available",
                "DedicatedHostType":"ddh.se1ne",
                "RegionId":"cn-beijing",
                "DedicatedHostName":"dhZ2ze3lmtckdjw1pt8nr82Z",
                "SaleCycle":"",
                "AutoReleaseTime":"",
                "Capacity":{
                    "AvailableVcpus":56,
                    "TotalMemory":448,
                    "TotalVcpus":56,
                    "AvailableLocalStorage":0,
                    "TotalLocalStorage":0,
                    "LocalStorageCategory":"",
                    "AvailableMemory":448
                },
                "OperationLocks":{
                    "OperationLock": []

                    ]
                },
                "MachineId":"xxxx",
                "ExpireTime":"2999-09-08T16:00:00Z",
            },
            {
                "DedicatedHostId":"dh-dedicatedhost2",
                "ChargeType": "PostPaid",
                "Description": "",
                "ResourceGroupId":"",
                "SupportInstanceTypeFamilies":{
                    "SupportInstanceTypeFamily":[
                        "ecs.se1ne",
                    ]
                },
                "Instances": {
                    "Instance": [

                    ]
                },
                "Cores":32,
                "ZoneId":"cn-beijing-c"
                "CreationTime":"2018-08-13T07:59Z",
                "Sockets":2,
                "Status": "Available",
                "DedicatedHostType":"ddh.se1ne",
                "RegionId":"cn-beijing",
                "DedicatedHostName":"xxxxx",
                "SaleCycle":"",
                "AutoReleaseTime":"",
                "Capacity":{
                    "AvailableVcpus":56,
                    "TotalMemory":448,
                    "TotalVcpus":56,
                    "AvailableLocalStorage":0,
                    "TotalLocalStorage":0,
                    "LocalStorageCategory":"",
                    "AvailableMemory":448
                },
                "OperationLocks":{
                    "OperationLock": []

                    ]
                },
                "MachineId":"f9b97a46c05b38c8c9cfe2b120f26xxxx",
                "ExpireTime":"2999-09-08T16:00:00Z",
            }
        ]
    },
    "TotalCount":2,
    "PageSize":10,
    "RequestId":"9D5CC4F5-921A-4E02-B971-0DAF703407BE"
}
```

## Error codes {#ErrorCode .section}

|Error code|Error message|HTTP status code |Description|
|:---------|:------------|:----------------|:----------|
|DedicatedHostType.Invalid|The specified DedicatedHostType is invalid.|400|The error message returned when the specified DedicatedHostType parameter is invalid.|
|InternalError|The request processing task has failed due to an unknown error, exception or failure.|500|The error message returned when an unknown internal error occurs.|

