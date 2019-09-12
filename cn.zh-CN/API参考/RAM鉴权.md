# RAM鉴权 {#concept_1958412 .concept}

在使用RAM账号调用专有宿主机API前，需要主账号通过创建授权策略对RAM账号进行授权。在授权策略中，使用资源描述符（Alibaba Cloud Resource Name，ARN）指定授权资源。

|资源类型|授权策略中的资源描述方法|
|----|------------|
|AllocateDedicatedHosts|acs:ecs:$regionid:$accountid:ddh/\*|
|DescribeDedicatedHosts|acs:ecs:$regionid:$accountid:ddh/$dedicatedhostid|
|DescribeDedicatedHostTypes|无需鉴权|
|DescribeDedicatedHostAutoRenew|acs:ecs:$regionid:$accountid:ddh/$dedicatedhostid|
|ModifyDedicatedHostAttribute|acs:ecs:$regionid:$accountid:ddh/$dedicatedhostid|
|ModifyDedicatedHostAutoReleaseTime|acs:ecs:$regionid:$accountid:ddh/$dedicatedhostid|
|ModifyDedicatedHostAutoRenewAttribute|acs:ecs:$regionid:$accountid:ddh/$dedicatedhostid|
|ModifyInstanceDeployment|acs:ecs:$regionid:$accountid:instance/$instanceid|
|acs:ecs:$regionid:$accountid:ddh/$dedicatedhostid|
|RenewDedicatedHost|acs:ecs:$regionid:$accountid:ddh/$dedicatedhostid|
|ReleaseDedicatedHosts|acs:ecs:$regionid:$accountid:ddh/$dedicatedhostid|

