# ModifyDedicatedHostAutoRenewAttribute {#ModifyDedicatedHostAutoRenewAttribute .reference}

为一台或多台预付费专有宿主机设置自动续费，也可以取消已设定的自动续费。

## 描述 {#section_o13_nsx_kfb .section}

预付费专有宿主机到期前九天自动续费，扣费在 08:00:00（UTC +8）时间点自动执行。如果前一日扣费失败，次日继续定时执行。扣费成功或者九天之后专有宿主机到期被锁定后停止自动扣费。期间，您需要保证自己的支付方式使用额度充足即可。

## 请求参数 {#RequestParameter .section}

|名称|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|系统规定参数。取值：ModifyDedicatedHostAutoRenewAttribute|
|RegionId|String|是|专有宿主机所属的地域 ID。|
|DedicatedHostIds|String|是|专有宿主机 ID。最多可以输入 100 个预付费专有宿主机 ID，ID 之间用半角逗号（,）隔开。|
|Period|String|否|续费周期，取值范围参阅 PeriodUnit 的参数描述部分。|
|PeriodUnit|String|否|续费单位。取值范围：-   Week：周。此时，参数 Period 的取值范围为 \{1, 2, 3\}。
-   Month（默认）：月。此时，参数 Period 的取值范围为 \{ 1, 2, 3, 6, 12\}。

|
|AutoRenew|Boolean|否|是否自动续费预付费的专有宿主机。默认值：False|
|RenewalStatus|String|否|是否自动续费预付费的专有宿主机，RenewalStatus 的优先级高于 AutoRenew。取值范围：-   AutoRenewal：自动续费。
-   Normal：待续费。
-   NotRenewal：不续费，也不发送到期提醒。到期前第三天我们会发送不续费提醒。不续费的专有宿主机可以设置成待续费（Normal），再自行续费（[RenewDedicatedHosts](cn.zh-CN/API参考/RenewDedicatedHosts.md#)）或设置为自动续费（AutoRenewal）。

|
|ClientToken|String|否| 保证请求幂等性。从您的客户端生成一个参数值，确保不同请求间该参数值唯一。只支持ASCII字符，且不能超过64个字符。更多详情，请参阅[如何保证幂等性](../../cn.zh-CN/API参考/附录/如何保证幂等性.md#)。

 |

## 返回参数 {#ResponseParameter .section}

全是公共返回参数。参阅[公共返回参数](../../cn.zh-CN/API参考/HTTP调用方式/公共参数.md#commonResponseParameters)。

## 示例 {#Samples .section}

**请求示例** 

```
https://ecs.aliyuncs.com/?Action=ModifyDedicatedHostAutoRenewAttribute
&RegionId=cn-hangzhou
&DedicatedHostIds=dh-dedicatedhost1,dh-dedicatedhost2
&AutoRenew=true
&<公共请求参数>
```

**返回示例**

**XML 格式**

```
<ModifyDedicatedHostAutoRenewAttributeResponse>
  <RequestId>2A4EA075-CB5B-41B7-B0EB-70D339F64DE7</RequestId>
</ModifyDedicatedHostAutoRenewAttributeResponse>
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
|IncorrectHostStatus|The current status of the resource does not support this operation.|403|由于实例已过期，不支持此操作。|
|InvalidPeriodUnit.ValueNotSupported|The specified parameter PeriodUnit is not valid.|403|指定的续费单位无效。|
|InvalidParameter.ToManyDedicatedHostIds|No more than 100 DedicatedHostIds can be specified.|403|单次最多能指定 100 个专有宿主机 ID。|
|MissingParameter.DedicatedHostId|DedicatedHostId should not be null.|403|指定的 DedicatedHostIds 不能为空。|
|InvalidParameter.InvalidDedicatedHostId|The specified dedicatedHostIds is not valid.|403|指定参数 DedicatedHostIds 里有无效的专有宿主机 ID。|
|InvalidParameter.Duration|The auto renewal duration should be one of the following values: 1|2|3|6|12.|403|指定的续费时长不符合要求，应为 \[1,2,3,6,12\] 中的一个。|
|InvalidParameter.RenewalStatus|The specified parameter RenewalStatus must be AutoRenewal NotRenewal or Normal.|403|指定的 RenewalStatus 无效。|
|InvalidDedicatedHostId.NotFound|The specified DedicatedHostId does not exist.|404|指定的 DedicatedHostIds 列表里有不存在的专有宿主机 ID。|

