# ModifyDedicatedHostAutoReleaseTime {#ModifyDedicatedHostAutoReleaseTime .reference}

为一台按量付费专有宿主机设定自动释放时间，或者取消自动释放一台专有宿主机。到预约时间点后，按量付费专有宿主机会被自动释放，请确保您是否不再使用宿主机，并且按需备份应用数据。

## 请求参数 {#RequestParameter .section}

|名称|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|系统规定参数。取值：ModifyDedicatedHostAutoReleaseTime|
|DedicatedHostId|String|是|需要自动释放的专有宿主机 ID。|
|AutoReleaseTime|String|否|自动释放时间。如果不输入 AutoReleaseTime 参数，表示取消自动释放，专有宿主机在预约时间点不再自动释放。-   最短不能晚于当前时间半小时内。
-   最长不能超过当前时间三年以后。
-   如果秒（`ss`）取值不是 `00`，则自动取为当前分钟（`mm`）开始时刻。

|

## 返回参数 {#ResponseParameter .section}

## 示例 {#Samples .section}

**请求示例** 

```
https://ecs.aliyuncs.com/?Action=ModifyDedicatedHostAutoReleaseTime
&DedicatedHostId=dh-dedicatedhost1
&<公共请求参数>
```

**返回示例**

**XML 格式**

```
<ModifyDedicatedHostAutoReleaseTimeResponse>
    <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
</ModifyDedicatedHostAutoReleaseTimeResponse>
```

**JSON 格式**

```
{ 
    "RequestId": "C0003E8B-B930-4F59-ADC0-0E209A9012A8"
}
```

## 错误码 {#ErrorCode .section}

|错误代码|错误信息|HTTP状态码|说明|
|:---|:---|:------|:-|
|MissingParameter|DedicatedHostId should not be null.|400|必须指定 DedicatedHostId。|
|InvalidAutoReleaseTime.Malformed|The specified paramter autoReleaseTime is not valid.|400|指定参数 AutoReleaseTime 无效。|
|UnsupportedParameter|The parameters is unsupported.|400|不支持指定的参数。|
|ChargeTypeViolation|The operation is not permitted due to charge type of the dedicated host.|403|只能释放按量付费专有宿主机。|
|NoSuchResource|The specified resource is not found.|404|指定的资源不存在。|
|InternalError|The request processing has failed due to some unknown error,exception or failure.|500|内部错误。|

