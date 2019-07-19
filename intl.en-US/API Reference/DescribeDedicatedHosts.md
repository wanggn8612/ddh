# DescribeDedicatedHosts {#DescribeDedicatedHosts .reference}

You can call this operation to query the details about one or more Dedicated Hosts \(DDHs\), including the physical performance specifications, virtual machine code, service status, and list of Elastic Compute Service \(ECS\) instances that you have created.

## Request parameters {#RequestParameter .section}

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set this parameter to DescribeDedicatedHosts.|
|RegionId|String|Yes|The region ID of the DDH.For more information, call [DescribeRegions](../../intl.en-US/API Reference/Regions/DescribeRegions.md#) to obtain the latest region list.|
|ZoneId|String|No|The zone ID of the DDH.|
|DedicatedHostIds|Array|No|The list of DDH IDs. You can enter a maximum of 100 DDH IDs at a time. Multiple DDH IDs are displayed as a JSON array, such as \["dh- xxxxxxxxx", "dh- yyyyyyyyy", …, "dh- zzzzzzzzz"\]. Separate multiple IDs with a comma \(`,`\).|
|DedicatedHostName|String|No|The name of the DDH.|
|DedicatedHostType|String|No|The type of the DDH.|
|Status|String|No|The service status of the DDH. Valid values: -   Available \(default value\): specifies that the DDH is available for use.
-   Under-Assessment: specifies that the DDH has potential failures and may fail when you use it.
-   Permanent-Failure: specifies that the DDH has permanent failures. You cannot use the DDH.

 |
|Tag.n.Key|String|No|DDHThe key of a tag of which n is from 1 to 20. Once you use this parameter, it cannot be a null string. It can be up to 64 characters in length. It cannot begin with "aliyun", "acs:", "http://", or "https://".|
|Tag.n.Value|String|No|DDHThe value of a tag of which n is a number from 1 to 20. Once you use this parameter, it can be a null string. It can be up to 128 characters in length. It cannot begin with "aliyun", "acs:", "http://", or "https://".|
|PageNumber|Integer|No|The number of the page to return. Default value: 1.

 |
|PageSize|Integer|No|The number of entries to return on each page. Maximum value: 100. Default value: 10.

 |

## Response parameters {#ResponseParameter .section}

|Parameter|Type|Description|
|:--------|:---|:----------|
|TotalCount|Integer|The total number of DDHs.|
|PageNumber|Integer|The page number of the returned DDH list.|
|PageSize|Integer|The number of entries returned on each page.|
|DedicatedHosts|Array of [DedicatedHostAttributesType](#)|The details about DDHs.|

 **DedicatedHostAttributesType** 

|Parameter|Type|Description|
|:--------|:---|:----------|
|DedicatedHostId|String|The ID of the DDH.|
|MachineId|String|The virtual machine code of the DDH.|
|DedicatedHostName|String|The name of the DDH.|
|DedicatedHostType|String|The type of the DDH.|
|Description|String|The description of the DDH.|
|RegionId|String|The region ID of the DDH.|
|ZoneId|String|The zone ID of the DDH.|
|Sockets|Integer|The number of physical CPUs.|
|Cores|Integer|The number of cores in a CPU.|
|SupportedInstanceTypeFamilies|Array of [SupportedInstanceTypeFamilySetType](#)|The ECS instance type family supported by the DDH.|
|Capacity|Array of [DedicatedHostCapacity](#)|The performance specifications of the DDH.|
|Instances|Array of [HostInstance](#)|The details about ECS instances that you have created on the DDH.|
|Status|String|The service status of the DDH. Valid values: Available, Under-Assessment, and Permanent-Failure.|
|CreationTime|String|The time when the DDH was created.The time format follows the [ISO8601](../../intl.en-US/API Reference/Appendix/ISO 8601 Time Format.md#) standard, and the UTC time is used. The format is yyyy-MM-ddTHH:mm:ssZ.|
|ChargeType|String|The billing method of the DDH.|
|SaleCycle|String|The billing cycle of the subscription DDH.|
|ExpiredTime|String|The expiration time of the subscription DDH.The time format follows the [ISO8601](../../intl.en-US/API Reference/Appendix/ISO 8601 Time Format.md#) standard, and the UTC time is used. The format is yyyy-MM-ddTHH:mm:ssZ.|
|OperationLocks|Array of [OperationLocksType]()|The reason why DDH resources were locked.|
|AutoPlacement|String|Indicates whether the DDH was added to the automatic deployment resource pool. Valid values: -   on: indicates that the DDH was added to the automatic deployment resource pool.
-   off: indicates that the DDH was not added to the automatic deployment resource pool.

 |

 **DedicatedHostCapacity** 

|Parameter|Type|Description|
|:--------|:---|:----------|
|TotalVcpus|Integer|The total number of cores in the vCPU.|
|AvailableVcpus|Integer|The remaining number of cores in the vCPU.|
|TotalMemory|Float|The total capacity of the memory. Unit: GiB.|
|AvailablevMemory|Float|The remaining capacity of the memory. Unit: GiB.|
|TotalDisk|Integer|The total capacity of the local disk. Unit: GiB.|
|AvailableDisk|Integer|The remaining capacity of the local disk. Unit: GiB.|
|LocalStorageCategory|String|The type of the local disk.|

 **HostInstance** 

|Parameter|Type|Description|
|:--------|:---|:----------|
|InstanceId|String|The ID of the ECS instance that you created on the DDH.|
|InstanceType|String|The type of the ECS instance that you created on the DDH.|

 **SupportedInstanceTypeFamilySetType** 

|Parameter|Type|Description|
|:--------|:---|:----------|
|SupportedInstanceTypeFamily|String|The ECS instance type family supported by the DDH.|

 **OperationLocksType** 

|Parameter|Type|Description|
|:--------|:---|:----------|
|LockReason|Array of [LockReasonType]()|The reason why DDH resources were locked.|

 **LockReasonType** 

|Parameter|Type|Description|
|:--------|:---|:----------|
|LockReason|String|The type of the reason why DDH resources were locked. Valid value: financial: indicates that your account has an overdue payment.

 |

## Examples {#Samples .section}

 **Sample request** 

```
https://ecs.aliyuncs.com/?Action=DescribeDedicatedHosts
&RegionId=cn-hangzhou
&<Common request parameters>
```

 **Sample success response** 

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
      <ExpiredTime>2999-09-08T16:00Z</ExpiredTime>
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
      <ExpiredTime>2999-09-08T16:00Z</ExpiredTime>
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
                "ChargeType":"PostPaid",
                "Description":"",
                "ResourceGroupId":"",
                "SupportInstanceTypeFamilies":{
                    "SupportInstanceTypeFamily":[
                        "ecs.se1ne"
                    ]
                },
                "Instances":{
                    "Instance":[

                    ]
                },
                "Cores":32,
                "ZoneId":"cn-beijing-c",
                "CreationTime":"2018-08-13T07:59Z",
                "Sockets":2,
                "Status":"Available",
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
                    "OperationLock":[

                    ]
                },
                "MachineId":"xxxx",
                "ExpiredTime":"2999-09-08T16:00Z"
            },
            {
                "DedicatedHostId":"dh-dedicatedhost2",
                "ChargeType":"PostPaid",
                "Description":"",
                "ResourceGroupId":"",
                "SupportInstanceTypeFamilies":{
                    "SupportInstanceTypeFamily":[
                        "ecs.se1ne"
                    ]
                },
                "Instances":{
                    "Instance":[

                    ]
                },
                "Cores":32,
                "ZoneId":"cn-beijing-c",
                "CreationTime":"2018-08-13T07:59Z",
                "Sockets":2,
                "Status":"Available",
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
                    "OperationLock":[

                    ]
                },
                "MachineId":"f9b97a46c05b38c8c9cfe2b120f26xxxx",
                "ExpiredTime":"2999-09-08T16:00Z"
            }
        ]
    },
    "TotalCount":2,
    "PageSize":10,
    "RequestId":"9D5CC4F5-921A-4E02-B971-0DAF703407BE"
}
```

## Error codes {#ErrorCode .section}

|Error code|Error message|HTTP status code|Description|
|:---------|:------------|:---------------|:----------|
|DedicatedHostType.Invalid|The specified DedicatedHostType is invalid.|400|The error message returned because the specified DedicatedHostType parameter is invalid.|
|InternalError|The request processing has failed due to some unknown error,exception or failure.|500|The error message returned because an internal error has occurred.|

