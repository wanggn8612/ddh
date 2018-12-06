# RenewDedicatedHosts {#RenewDedicatedHosts .reference}

续费一台或者多台预付费专有宿主机。付款时，优先使用可抵扣的代金券，且您的账号必须支持账号余额支付或信用支付。

## 请求参数 {#RequestParameter .section}

|名称|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|系统规定参数。取值：RenewDedicatedHosts|
|DedicatedHostIds|String|是|专有宿主机的编号列表。最多可以输入 100 个预付费专有宿主机 ID。多个专有宿主机 ID 用一个格式类似\[“dh- xxxxxxxxx”, “dh- yyyyyyyyy”, … “dh- zzzzzzzzz”\]的 JSON 数组表示，ID 之间用半角逗号（`,`）隔开。|
|Period|Integer|是|续费周期，取值范围参阅 PeriodUnit 的参数描述部分。|
|PeriodUnit|String|否|续费单位。取值范围：-   Week：周。此时，参数 Period 的取值范围为 \{1, 2, 3, 4\}。
-   Month（默认）：月。此时，参数 Period 的取值范围为 \{ 1, 2, 3, 4, 5, 6, 7, 8, 9, 12, 24, 36, 48, 60\}。

|
|ClientToken|String|否|保证请求幂等性。从您的客户端生成一个参数值，确保不同请求间该参数值唯一。只支持ASCII字符，且不能超过64个字符。更多详情，请参阅[如何保证幂等性](../../cn.zh-CN/API 参考/附录/如何保证幂等性.md#)。

|

## 返回参数 {#ResponseParameter .section}

全是公共返回参数。参阅[公共返回参数](../../cn.zh-CN/API 参考/快速入门/公共参数.md#commonResponseParameters)。

## 示例 {#Samples .section}

**请求示例** 

```
https://ecs.aliyuncs.com/?Action=RenewDedicatedHosts
&RegionId=cn-hangzhou
&DedicatedHostIds=dh-dedicatedhost1,dh-dedicatedhost2
&Period=1
&PeriodUnit=Month
&<公共请求参数>
```

**返回示例**

**XML 格式**

```
<RenewDedicatedHostsResponse>
  <RequestId>2A4EA075-CB5B-41B7-B0EB-70D339F64DE7</RequestId>
</RenewDedicatedHostsResponse>
```

**JSON 格式**

```
{
    "RequestId":"2A4EA075-CB5B-41B7-B0EB-70D339F64DE7"
}
```

## 错误码 {#ErrorCode .section}

|错误代码|错误信息|HTTP状态码|说明|
|:---|:---|:------|:-|
|IdempotenceParamNotMatch|Request uses a client token in a previous request but is not identical to that request.|400|您重用了 ClientToken 参数，但其他请求参数有变化。|
|InvalidClientToken.ValueNotSupported|The ClientToken provided is invalid.|400|ClientToken 不能包含 ASCII 以外的字符。|
|IncorrectHostStatus|The current status of the resource does not support this operation.|403|专有宿主机目前的状态无法续费。|
|InvalidPeriod|The specified period is not valid.|400|指定的 Peroid 参数格式无效。|
|LastTokenProcessing|The last token request is processing.|403|还在处理上一次请求，请稍后重试。|
|InvalidPeriodUnit.ValueNotSupported|The specified parameter PeriodUnit is not valid.|400|指定的 PeriodUnit 参数格式无效。|
|InvalidDedicatedHostId.NotFound|The specified DedicatedHostId does not exist.|400|指定的专有宿主机 ID 不存在。|
|InvalidStatus.Upgrading|The dedicated host is upgrading, please try it later.|400|正在升级指定的专有宿主机，请稍后重试。|

