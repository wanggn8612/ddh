# ReleaseDedicatedHost {#ReleaseDedicatedHost .reference}

释放一台按量付费专有宿主机，待释放的专有宿主机上不能宿有 ECS 实例。

## 请求参数 {#RequestParameter .section}

|名称|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|系统规定参数。取值：ReleaseDedicatedHost|
|RegionId|String|是|专有宿主机所属的地域 ID。您可以调用[DescribeRegions](../../cn.zh-CN/API 参考/地域/DescribeRegions.md#)查看最新的阿里云地域列表。|
|DedicatedHostId|String|是|专有宿主机 ID。|

## 返回参数 {#ResponseParameter .section}

全是公共返回参数。参阅[公共返回参数](../../cn.zh-CN/API 参考/快速入门/公共参数.md#commonResponseParameters)。

## 示例 {#Samples .section}

**请求示例** 

```
https://ecs.aliyuncs.com/?Action=ReleaseDedicatedHost
&RegionId=cn-hangzhou
&DedicatedHostId=dh-dedicatedhost1
&<公共请求参数>
```

**返回示例**

**XML 格式**

```
<ReleaseDedicatedHostResponse>
  <RequestId>A1B15AC8-E6F6-49A4-8985-8C07104B9199</RequestId>
</ReleaseDedicatedHostResponse>
```

**JSON 格式**

```
{
    "RequestId":"A1B15AC8-E6F6-49A4-8985-8C07104B9199"
}
```

## 错误码 {#ErrorCode .section}

以下为本接口特有的错误码。更多错误码，请访问[API错误中心](https://error-center.aliyun.com/status/product/Ecs)。

|错误代码|错误信息|HTTP 状态码|说明|
|:---|:---|:-------|:-|
|InstanceExist|Instance exists on the dedicated host.|400|专有宿主机上有未释放的 ECS 实例。|
|OperationDenied.NotAuthorized|End user is not authorized to release the dedicated host.|403|您未被授权释放该专有宿主机。|
|InvalidDedicatedHostId.NotFound|The specified DedicatedHostId does not exist.|404|指定专有宿主机 ID 不存在。|
|InternalError|The request processing has failed due to some unknown error,exception or failure.|500|内部错误。|

