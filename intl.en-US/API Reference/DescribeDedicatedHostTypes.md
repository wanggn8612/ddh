# DescribeDedicatedHostTypes {#DescribeDedicatedHostTypes .reference}

You can call this operation to query details about supported DDH types in the specified region, or supported ECS instance type families on a DDH.

## Request parameters {#RequestParameter .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set the value to DescribeDedicatedHostTypes|
|RegionId|String|Yes|The ID of the region.For more information, call [DescribeRegions](../../intl.en-US/API Reference/Regions/DescribeRegions.md#) to obtain the latest region list.|
|DedicatedHostType|String|No|The type of the DDH. For more information, see [Dedicated Host types](https://www.alibabacloud.com/help/doc-detail/68564.htm).|
|SupportedInstanceTypeFamily|String|No|The ECS instance type family supported by a DDH type.|

## Response parameters {#ResponseParameter .section}

|Name|Type|Description|
|:---|:---|:----------|
|DedicatedHostTypes|Array of [DedicatedHostType](#)|The information about the DDH type.|

**DedicatedHostType**

|Name|Type|Required|
|:---|:---|:-------|
|DedicatedHostType|String|The type of the DDH. [open a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex)Submit a ticket if you need more DDH types.|
|SupportedInstanceTypeFamilies|Array of [SupportedInstanceTypeFamilySetType](#)|The ECS instance type family supported by the DDH type.|
|Sockets|Integer|The number of physical CPUs.|
|Cores|Integer|The number of cores in a physical CPU.|
|TotalVcpus|Integer|The total number of cores in a virtual CPU.|
|MemorySize|Float|The capacity of memory. Unit: GiB.|
|LocalStorageCapacity|Long|The capacity of a local disk. Unit: GiB.|
|LocalStorageAmount|Integer |The number of local disks on a DDH.|
|LocalStorageCategory|String|The type of a local disk.|

**SupportedInstanceTypeFamilySetType**

|Name|Type|Required|
|:---|:---|:-------|
|SupportedInstanceTypeFamily|String|The ECS instance type family supported by a DDH type.|

## Samples {#Samples .section}

**Sample requests**

```
https://ecs.aliyuncs.com/?Action=DescribeDedicatedHostTypes
&RegionId=cn-hangzhou
&<Common Request Parameters>
```

**Sample responses**

**XML format**

```
<DescribeDedicatedHostTypesResponse>
  <DedicatedHostTypes>
    <DedicatedHostType>
      <LocalStorageAmount>0</LocalStorageAmount>
      <Sockets>2</Sockets>
      <DedicatedHostType>ddh.sn1ne</DedicatedHostType>
      <LocalStorageCapacity>0</LocalStorageCapacity>
      <SupportedInstanceTypeFamilies>
        <SupportedInstanceTypeFamily>ecs.sn1ne</SupportedInstanceTypeFamily>
      </SupportedInstanceTypeFamilies>
      <MemorySize>112.0</MemorySize>
      <Cores>32</Cores>
      <TotalVcpus>56</TotalVcpus>
      <LocalStorageCategory/>
    </DedicatedHostType>
    <DedicatedHostType>
      <LocalStorageAmount>0</LocalStorageAmount>
      <Sockets>2</Sockets>
      <DedicatedHostType>ddh.sn2ne</DedicatedHostType><Dedicatedhosttype> DDH. sn2ne </dedicatedhosttype>
      <LocalStorageCapacity>0</LocalStorageCapacity>
      <SupportedInstanceTypeFamilies>
        <SupportedInstanceTypeFamily>ecs.sn2ne</SupportedInstanceTypeFamily>
      </SupportedInstanceTypeFamilies></FIG>
      <MemorySize>224.0</MemorySize>
      <Cores>32</Cores>
      <TotalVcpus>56</TotalVcpus>
      <LocalStorageCategory/>
    </DedicatedHostType>
  </DedicatedHostTypes>
  <RequestId>5FE5FF06-3A33-4658-8495-6445FC54E327</RequestId>
</DescribeDedicatedHostTypesResponse>
```

**JSON format**

```
{
    "DedicatedHostTypes":{
        "DedicatedHostType":[
            {
                "LocalStorageAmount":0,
                "Sockets":2,
                "DedicatedHostType":"ddh.sn1ne",
                "LocalStorageCapacity":0,
                "SupportedInstanceTypeFamilies":{
                    "SupportedInstanceTypeFamily":[
                        "ecs.sn1ne",
                    ]
                },
                "MemorySize": 1
                "Cores":32,
                "TotalVcpus":56,
                "LocalStorageCategory":""
            },
            {
                "LocalStorageAmount":0,
                "Sockets":2,
                "DedicatedHostType":"dh.c60m83.n1",
                "LocalStorageCapacity":0,
                "SupportedInstanceTypeFamilies":{
                    "SupportedInstanceTypeFamily":[
                        "ecs.n1"
                    ]
                },
                "MemorySize": 1
                "Cores":32,
                "TotalVcpus":40,"Maid": 40,
                "LocalStorageCategory":"""Maid ":""
            }
        ]
    },
    "RequestId":"9A0FE8A2-720C-45AE-B2D9-813060FCBBF5"
}
```

## Error codes {#ErrorCode .section}

|Error code|Error message|HTTP status code |Description|
|:---------|:------------|:----------------|:----------|
|InternalError|The request processing task has failed due to an unknown error, exception or failure.|500|The error message returned when an unknown internal error occurs.|

