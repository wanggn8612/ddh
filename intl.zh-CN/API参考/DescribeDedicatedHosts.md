# DescribeDedicatedHosts {#DescribeDedicatedHosts .reference}

查询一台或多台专有宿主机的详细信息。包括专有宿主机的物理性能指标、虚拟机器码、使用状态和已创建的ECS实例列表等。

## 请求参数 {#RequestParameter .section}

|名称|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|系统规定参数。取值：DescribeDedicatedHosts|
|RegionId|String|是|专有宿主机所属的地域ID。您可以调用[DescribeRegions](../../intl.zh-CN/API参考/地域/DescribeRegions.md#)查看最新的阿里云地域列表。|
|ZoneId|String|否|可用区ID。|
|DedicatedHostIds|Array|否|专有宿主机ID列表。单次最多支持100个ID ，多个ID用一个格式类似\[“dh- xxxxxxxxx”, “dh- yyyyyyyyy”, … “dh- zzzzzzzzz”\]的JSON 数组表示，ID之间用半角逗号（`,`）隔开。|
|DedicatedHostName|String|否|专有宿主机名称。|
|DedicatedHostType|String|否|专有宿主机类型。|
|Status|String|否|专有宿主机的使用状态。取值范围： -   available（默认）：可用状态 。
-   under-assessment：故障潜伏期，专有宿主机可能会出故障。
-   permanent-failure：永久性故障，专有宿主机不可用。

 |
|Tag.n.Key|String|否|专有宿主机的标签键。n 的取值范围：\[1, 20\]。一旦传入该值，则不允许为空字符串。最多支持 64 个字符，不能以 aliyun、acs:、http:// 或者 https:// 开头。|
|Tag.n.Value|String|否|专有宿主机的标签值。n的取值范围：\[1, 20\]。一旦传入该值，可以为空字符串。最多支持 128 个字符，不能以 aliyun、acs:、http:// 或者 https:// 开头。|
|PageNumber|Integer|否|响应信息的页码数。 默认值：1

 |
|PageSize|Integer|否|响应信息的每页行数。最大值：100 默认值：10

 |

## 返回参数 {#ResponseParameter .section}

|名称|类型|描述|
|:-|:-|:-|
|TotalCount|Integer|专有宿主机总数。|
|PageNumber|Integer|专有宿主机列表的页码。|
|PageSize|Integer|输入时设置的每页行数。|
|DedicatedHosts|Array of [DedicatedHostAttributesType](#)|专有宿主机的详细信息集合。|

 **DedicatedHostAttributesType** 

|名称|类型|描述|
|:-|:-|:-|
|DedicatedHostId|String|专有宿主机ID。|
|MachineId|String|专有宿主机虚拟机器码。|
|DedicatedHostName|String|专有宿主机名称。|
|DedicatedHostType|String|专有宿主机类型。|
|Description|String|专有宿主机描述。|
|RegionId|String|地域ID。|
|ZoneId|String|可用区ID。|
|Sockets|Integer|物理处理器（CPU）数量。|
|Cores|Integer|单个CPU的核数。|
|SupportedInstanceTypeFamilies|Array of [SupportedInstanceTypeFamilySetType](#)|专有宿主机支持的ECS实例规格族。|
|Capacity|Array of [DedicatedHostCapacity](#)|专有宿主机性能指标集合。|
|Instances|Array of [HostInstance](#)|专有宿主机上已创建的ECS实例信息集合。|
|Status|String|专有宿主机的使用状态。可能值：Available | Under-Assessment | Permanent-Failure|
|CreationTime|String|创建时间。按照[ISO8601](../../intl.zh-CN/API参考/附录/时间格式.md#)标准表示，并需要使用UTC时间，格式为yyyy-MM-ddTHH:mm:ssZ。|
|ChargeType|String|专有宿主机的计费方式。|
|SaleCycle|String|预付费专有宿主机的计费周期。|
|ExpiredTime|String|预付费专有宿主机的到期时间。按照[ISO8601](../../intl.zh-CN/API参考/附录/时间格式.md#)标准表示，并需要使用UTC时间，格式为yyyy-MM-ddTHH:mm:ssZ。|
|OperationLocks|Array of [OperationLocksType]()|专有宿主机资源被锁定原因。|
|AutoPlacement|String|专有宿主机是否加入自动部署资源池。取值范围： -   on：加入自动部署资源池。
-   off：不加入自动部署资源池。

 |

 **DedicatedHostCapacity** 

|名称|类型|描述|
|:-|:-|:-|
|TotalVcpus|Integer|vCPU总核数。|
|AvailableVcpus|Integer|剩余的vCPU核数。|
|TotalMemory|Float|内存总容量，单位：GiB。|
|AvailablevMemory|Float|剩余的内存容量，单位：GiB。|
|TotalDisk|Integer|本地盘总容量，单位：GiB。|
|AvailableDisk|Integer|剩余的本地盘容量，单位：GiB。|
|LocalStorageCategory|String|本地盘类型。|

 **HostInstance** 

|名称|类型|描述|
|:-|:-|:-|
|InstanceId|String|专有宿主机上创建的ECS实例ID。|
|InstanceType|String|专有宿主机上创建的ECS实例类型。|

 **SupportedInstanceTypeFamilySetType** 

|名称|类型|描述|
|:-|:-|:-|
|SupportedInstanceTypeFamily|String|专有宿主机上支持创建的ECS实例规格族。|

 **OperationLocksType** 

|名称|类型|描述|
|:-|:-|:-|
|LockReason|Array of [LockReasonType]()|资源锁定原因。|

 **LockReasonType** 

|名称|类型|描述|
|:-|:-|:-|
|LockReason|String|锁定类型。可能值： financial：因账号欠费被锁定。

 |

## 示例 {#Samples .section}

 **请求示例** 

```
https://ecs.aliyuncs.com/?Action=DescribeDedicatedHosts
&RegionId=cn-hangzhou
&<公共请求参数>
```

 **返回示例** 

**XML 格式**

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

 **JSON 格式** 

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

## 错误码 {#ErrorCode .section}

|错误代码|错误信息|HTTP 状态码|说明|
|:---|:---|:-------|:-|
|DedicatedHostType.Invalid|The specified DedicatedHostType is invalid.|400|指定的DedicatedHostType无效。|
|InternalError|The request processing has failed due to some unknown error,exception or failure.|500|内部错误。|

