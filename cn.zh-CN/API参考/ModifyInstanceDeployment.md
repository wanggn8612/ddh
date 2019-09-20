# ModifyInstanceDeployment {#ModifyInstanceDeployment .reference}

调用ModifyInstanceDeployment接口修改一台ECS实例的部署集或宿主机。宿主机与ECS实例必须位于同一地域。

## 描述 {#section_i5w_p32_lfb .section}

ModifyInstanceDeployment支持以下功能：

-   修改ECS实例的部署集。 例如，将实例加入一个部署集，或调整实例的部署集时，请求参数DeploymentSetId为必填参数。

    **说明：** 修改专有宿主机实例相关参数（Tenancy、Affinity和DedicatedHostId）时，不可同时修改部署集。

-   修改ECS实例的宿主机。具体场景，如下表所示。

    |场景分类|参数设置|执行结果|
    |:---|:---|:---|
    |将ECS实例从共享宿主机迁移至专有宿主机|DedicatedHostId：指定专有宿主机ID|实例迁移至指定专有宿主机上。|
    |同时设置以下两个参数。     -   DedicatedHostId：空
    -   Tenancy：host
 |阿里云自动为您选择专有宿主机部署实例。|
    |在两台专有宿主机之前迁移实例|DedicatedHostId：指定专有宿主机ID|实例迁移至指定专有宿主机上。|
    |同时设置以下两个参数。     -   DedicatedHostId：空
    -   Tenancy：host
 |阿里云自动为您选择专有宿主机部署实例。|


迁移实例至专有宿主机时，您需要注意：

-   ECS实例必须处于`已停止（Stopped）`状态，迁移后实例自动重启。
-   只支持专有网络VPC类型的ECS实例。
-   按量付费ECS实例可以迁移到包年包月专有宿主机上。包年包月ECS实例只能在包年包月专有宿主机之间迁移，且实例到期时间不能超过目标专有宿主机的到期时间。
-   将ECS实例从共享宿主机迁移至专有宿主机时，实例的计费方式只能是按量付费，不支持包年包月实例和抢占式实例。

## 请求参数 {#RequestParameter .section}

|名称|类型|是否必需|示例值|描述|
|:-|:-|:---|:--|:-|
|Action|String|是|ModifyInstanceDeployment|系统规定参数。取值：ModifyInstanceDeployment|
|RegionId|String|是|cn-hangzhou|实例所在的地域ID。您可以调用[DescribeRegions](../../intl.zh-CN/API参考/地域/DescribeRegions.md#)查看最新的阿里云地域列表。|
|InstanceId|String|是|i-2zexxxxxxxxxxxxxxxxx|实例ID。实例必须处于`Stopped（已停止）`或者`Running（运行中）`状态。|
|DeploymentSetId|String|否|ds-bp1xxxxxxxxxxxxxxxxx|部署集ID。|
|DedicatedHostId|String|否|dh-bpxxxxxxxxxxxxxxxxxx|专有宿主机ID。您可以调用[DescribeDedicatedHosts](intl.zh-CN/API参考/DescribeDedicatedHosts.md#)查看可以使用的专有宿主机。|
|Force|Boolean|否|true|是否强制更换实例宿主机。 取值范围： -   true：允许实例更换宿主机，允许重启`Running（运行中）`的实例、`Stopped（已停止）`的包年包月实例和`Stopped（已停止）`的停机收费的按量付费实例。
-   false（默认）：不允许实例更换宿主机，只在当前宿主机上加入部署集。这可能导致更换部署集失败。

 |
|Tenancy|String|否|host|实例是否部署在专有宿主机上。更多详情，请参见[修改实例宿主机场景](#table_ao0_xtm_g0z)。取值范围： host（实例部署在专有宿主机上）|
|Affinity|String|否|default|实例是否固定在专有宿主机上。取值范围： -   host：实例固定在专有宿主机上。实例停机并释放资源后，再次启动时，仍部署在原专有宿主机上。若原专有宿主机可用资源不足，则实例启动失败。
-   default：实例不固定在专有宿主机上。实例停机并释放资源后，再次启动时，部署方式如下。
    -   若原专有宿主机可用资源充足，则优先部署在原专有宿主机上。
    -   若原专有宿主机可用资源不足，则部署在其它符合自动部署条件的专有宿主机上。

 实例从共享宿主机迁移至专有宿主机时，默认值：default

 |

## 返回参数 {#ResponseParameter .section}

全是公共返回参数。参阅[公共返回参数](../../intl.zh-CN/API参考/HTTP调用方式/公共参数.md#commonResponseParameters)。

## 示例 {#section_01c_jnp_z6h .section}

请求示例

``` {#codeblock_zkt_4rn_988}
https://ecs.aliyuncs.com/?Action=ModifyInstanceDeployment
&RegionId=cn-hangzhou
&DeploymentSetId=ds-bp1xxxxxxxxxxxxxxxxx
&<公共请求参数>
```

返回示例

-   XML 格式

    ``` {#codeblock_cnz_kjb_clw}
    <ModifyInstanceDeploymentResponse>
        <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
    </ModifyInstanceDeploymentResponse>
    ```

-   JSON 格式

    ``` {#codeblock_o34_7ot_1tc}
    {
        "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368"
    }
    ```


## 错误码 {#ErrorCode .section}

|错误代码|错误信息|HTTP状态码|说明|
|:---|:---|:------|:-|
|DeploymentSet.InvalidId|The specified Deployment Set id doesn't exist.|400|指定的DeploymentSetId不存在。|
|DeploymentSet.InstanceLimitExceeded|The number of instances on the specified Deployment Set has reached the limit.|403|指定的部署集内所含实例已达上限。|
|IncorrectInstanceStatus|The current status of the resource does not support this operation.|403|该资源目前的状态不支持此操作。|
|DeploymentSet.ModificationFailed|The modification of deployment set is currently impossible.|403|无法调整部署集。|
|InvalidInstanceId.NotFound|The specified InstanceId does not exist.|404|指定的实例ID不存在。|
|InvalidDedicatedHostId.NotFound|The specified DedicatedHostId does not exist.|404|指定的专有宿主机ID不存在。|
|LackResource|There's no enough resource on the specified dedicated host.|400|指定的专有宿主机已满负荷。|
|OperationDenied.UnstoppedInstance|Operation denied due to unstopped instancein your request.|400|迁移到专有宿主机时，ECS实例必须处于`已停止（Stopped）`状态，|
|InvalidPeriod.ExceededDedidactedHost|Instance expired date can't exceed dedicated host expired date.|400|包年包月ECS实例的到期时间不能晚于专有宿主机到期时间。|
|InvalidInstanceNetworkType.NotSupport|The specified Instance network type not support.|404|迁移到专有宿主机时，只支持专有网络VPC类型的ECS实例。|
|InvalidInstanceChargeType.NotSupport|The Dedicated host not support the specified Instance charge type.|404|将ECS实例从一台共享宿主机迁移到专有宿主机上时，实例的计费方式只能是按量付费，不支持包年包月实例和抢占式实例。|
|InvalidInstanceType.NotSupport|The Dedicated host not support the specified Instance type|404|专有宿主机不支持目标ECS实例的规格。|
|InvalidDedicatedHostStatus.NotSupport|Operation denied due to dedicated host status|400|您的账号已欠费，或者专有宿主机不可用。|
|InternalError|The request processing has failed due to some unknown error,exception or failure.|500|内部错误。|
|LackResource|There's no enough dedicated host resource.|400|自动部署资源池中的专有宿主机资源不足。|
|InvalidParameter.Param|Requested param is invalid.|400|请求参数无效。|
|InvalidParam.Tenancy|Instance tenancy is illegal in such case.|400|您填写的Tenancy属性值不正确。|
|InvalidParam.DedicatedHostId|The specified dedicated host id is the same with present host id!|400|您指定的专有宿主机ID和实例所在专有宿主机ID相同。|
|InvalidDedicatedHostId.NotSupport|Cannot choose instance present host as destination host.|404|您不能使用当前专有宿主机作为实例的目标宿主机。|
|InvalidDedicatedHost.NotFound|No available host.|404|无可用专有宿主机。|

