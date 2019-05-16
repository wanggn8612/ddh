# ModifyDedicatedHostAttribute {#ModifyDedicatedHostAttribute .reference}

修改一台专有宿主机的部分信息，包括专有宿主机的名称、描述和服务不可用属性等。

## 请求参数 {#RequestParameter .section}

|名称|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|系统规定参数。取值：ModifyDedicatedHostAttribute|
|RegionId|String|是|专有宿主机所属的地域ID。您可以调用[DescribeRegions](../../cn.zh-CN/API参考/地域/DescribeRegions.md#)查看最新的阿里云地域列表。|
|DedicatedHostId|String|是|专有宿主机ID。|
|DedicatedHostName|String|否|专有宿主机名称。长度为 \[2, 128\] 个英文或中文字符。必须以大小字母或中文开头，不能以 http:// 和 https:// 开头。可以包含数字、半角冒号（:）、下划线（\_）或者连字符（-）。|
|Description|String|否|专有宿主机的描述。长度为 \[2, 256\] 个英文或中文字符，不能以 http:// 和 https:// 开头。|
|ActionOnMaintenance|String|否|当专有宿主机发生故障或者在线修复时，为其所宿实例设置迁移方案。取值范围： -   Migrate：迁移实例到其他物理机并重新启动实例。
-   Stop：在当前专有宿主机上停止实例，确认无法修复专有宿主机后，迁移实例到其他物理机并重新启动实例。

 当专有宿主机上挂载的是云盘时，默认值：Migrate

 当专有宿主机上挂载的是本地盘时，默认值：Stop

 |
|NetworkAttributes.SlbUdpTimeout|Integer|否|负载均衡连接的UDP会话超时时间，单位：秒。取值范围：\[15, 310\]|
|NetworkAttributes.UdpTimeout|Integer|否|为专有宿主机上运行的云服务设置用户访问的UDP会话超时时间，单位：秒。取值范围：\[15, 310\]|
|AutoPlacement|String|否|设置专有宿主机是否加入自动部署资源池。当您在专有宿主机上创建实例，却不指定DedicatedHostId时，阿里云自动从资源池中选取专有宿主机放置实例。取值范围： -   on：加入自动部署资源池。
-   off：不加入自动部署资源池。

 |

## 返回参数 {#ResponseParameter .section}

全是公共返回参数。参阅[公共返回参数](../../cn.zh-CN/API参考/快速入门/公共参数.md#commonResponseParameters)。

## 示例 {#Samples .section}

 **请求示例** 

```
https://ecs.aliyuncs.com/?Action=ModifyDedicatedHostAttribute
&RegionId=cn-hangzhou
&DedicatedHostId=dh-dedicatedhost1
&Description=hello-world
&<公共请求参数>
```

 **返回示例** 

**XML 格式**

```
<ModifyDedicatedHostAttributeResponse>
  <RequestId>2A4EA075-CB5B-41B7-B0EB-70D339F64DE7</RequestId>
</ModifyDedicatedHostAttributeResponse>
```

 **JSON 格式** 

```
{
    "RequestId":"2A4EA075-CB5B-41B7-B0EB-70D339F64DE7"
}
```

## 错误码 {#ErrorCode .section}

|错误代码|错误信息|HTTP 状态码|说明|
|:---|:---|:-------|:-|
|InvalidInstanceName.Malformed|The specified parameter DedicatedHostName is not valid.|400|指定的DedicatedHostName无效。|
|InvalidDescription.Malformed|The specified parameter Description is not valid.|400|指定的Descrption无效。|
|InvalidUser.Unauthorized|The user is not authorized|401|您未被授权修改该专有宿主机的信息。|
|InvalidDedicatedHostId.NotFound|The specified DedicatedHostId does not exist.|404|指定专有宿主机ID不存在。|
|InternalError|The request processing has failed due to some unknown error,exception or failure.|500|内部错误。|

