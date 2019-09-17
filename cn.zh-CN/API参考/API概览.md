# API概览 {#concept_1957935 .concept}

本文介绍专有宿主机提供的相关API接口。

|API|描述|
|---|--|
|[AllocateDedicatedHosts](cn.zh-CN/API参考/AllocateDedicatedHosts.md#)|调用AllocateDedicatedHosts创建一台或多台按量付费或包年包月专有宿主机。|
|[DescribeDedicatedHostTypes](cn.zh-CN/API参考/DescribeDedicatedHostTypes.md#)|调用DescribeDedicatedHostTypes查询指定地域下支持的专有宿主机规格详细参数，或者查询专有宿主机支持的ECS实例规格族。|
|[DescribeDedicatedHosts](cn.zh-CN/API参考/DescribeDedicatedHosts.md#)|调用DescribeDedicatedHosts查询一台或多台专有宿主机的详细信息，包括专有宿主机的物理性能指标、虚拟机器码、使用状态和已创建的ECS实例列表等。|
|[DescribeDedicatedHostAutoRenew](cn.zh-CN/API参考/DescribeDedicatedHostAutoRenew.md#)|调用DescribeDedicatedHostAutoRenew查询一台或多台包年包月专有宿主机的自动续费状态。|
|[ModifyDedicatedHostAttribute](cn.zh-CN/API参考/ModifyDedicatedHostAttribute.md#)|调用ModifyDedicatedHostAttribute修改一台专有宿主机的部分信息，包括专有宿主机的名称、描述和服务不可用属性等。|
|[ModifyDedicatedHostAutoRenewAttribute](cn.zh-CN/API参考/ModifyDedicatedHostAutoRenewAttribute.md#)|调用ModifyDedicatedHostAutoRenewAttribute为一台或多台包年包月专有宿主机设置自动续费，或取消已设定的自动续费。|
|[ModifyDedicatedHostAutoReleaseTime](cn.zh-CN/API参考/ModifyDedicatedHostAutoReleaseTime.md#)|调用ModifyDedicatedHostAutoReleaseTime为一台按量付费专有宿主机设定自动释放时间，或者取消自动释放一台按量付费专有宿主机。|
|[ModifyInstanceDeployment](cn.zh-CN/API参考/ModifyInstanceDeployment.md#)|调用ModifyInstanceDeployment修改一台ECS实例的宿主机。ECS实例与目标专有宿主机必须在同一地域。|
|[RenewDedicatedHosts](cn.zh-CN/API参考/RenewDedicatedHosts.md#)|调用RenewDedicatedHosts续费一台或者多台包年包月专有宿主机。|
|[ReleaseDedicatedHost](cn.zh-CN/API参考/ReleaseDedicatedHost.md#)|调用ReleaseDedicatedHost释放一台按量付费专有宿主机。待释放的专有宿主机上不能存在ECS实例。|

