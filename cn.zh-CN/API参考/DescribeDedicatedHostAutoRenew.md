# DescribeDedicatedHostAutoRenew {#DescribeDedicatedHostAutoRenew .reference}

查询一台或多台包年包月专有宿主机自动续费状态。

## 请求参数 {#RequestParameter .section}

|名称|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|系统规定参数。取值：DescribeDedicatedHostAutoRenew|
|RegionId|String|是|专有宿主机所属的地域ID。|
|DedicatedHostIds|String|是|专有宿主机ID。最多可以输入100个包年包月专有宿主机ID，ID之间用半角逗号（,）隔开。|

## 返回参数 {#ResponseParameter .section}

|名称|类型|描述|
|:-|:-|:-|
|DedicatedHostId|String|专有宿主机ID。|
|Duration|Integer|自动续费时长。|
|AutoRenewEnabled|Boolean|是否自动续费。|
|PeriodUnit|String|续费单位。取值范围：Week | Month|
|RenewalStatus|String|是否自动续费包年包月专有宿主机。取值范围： -   AutoRenewal：自动续费。
-   Normal：待续费。
-   NotRenewal：不续费，也不发送到期提醒。到期前第三天我们会发送不续费提醒。不续费的专有宿主机可以设置成待续费（Normal），再自行续费（[RenewDedicatedHosts](intl.zh-CN/API参考/RenewDedicatedHosts.md#)）或设置为自动续费（AutoRenewal）。

 |

## 示例 {#Samples .section}

请求示例

``` {#codeblock_iyg_2ug_348}
https://ecs.aliyuncs.com/?Action=DescribeDedicatedHostAutoRenew
&RegionId=cn-hangzhou
&DedicatedHostIds=dh-dedicatedhost1,dh-dedicatedhost2
&<公共请求参数>
```

返回示例

-   XML 格式

    ``` {#codeblock_fn8_oiw_8f0}
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

-   JSON 格式

    ``` {#codeblock_44v_ew1_nss}
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


## 错误码 {#ErrorCode .section}

|错误代码|错误信息|HTTP 状态码|说明|
|:---|:---|:-------|:-|
|MissingParameter.DedicatedHostId|DedicatedHostId should not be null.|403|指定的DedicatedHostIds不能为空。|
|InvalidParameter.ToManyDedicatedHostIds|DedicatedHostId should be less than 100.|403|单次最多只能指定100个专有宿主机ID。|
|InvalidParameter.InvalidDedicatedHostId|The specified dedicatedHostId is not valid|403|指定的DedicatedHostIds中包含无效的专有宿主机ID。|

