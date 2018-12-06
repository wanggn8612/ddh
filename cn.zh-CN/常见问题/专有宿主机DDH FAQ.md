# 专有宿主机DDH FAQ {#concept_b2q_mnn_tdb .concept}

-   [什么是专有宿主机DDH？](#concept)
-   [DDH有什么优势？](#features)
-   [在什么场景下需要购买DDH？](#scenarios)
-   [DDH是裸机产品吗？](#bare)
-   [DDH与弹性裸金属服务器有什么区别？](#ebm)
-   [怎么创建和释放DDH？](#createAndRelease)
-   [怎么查看每台DDH上有多少可用资源？](#viewAvailableResources)
-   [能将共享宿主机上的ECS实例迁移到DDH上吗？](#ecsMigrationEcs)
-   [怎么在DDH上使用自带许可 \(BYOL\)？](#byol)
-   [DDH有唯一标识码吗？](#code)
-   [阿里云会在不同的DDH上重复使用同一个机器码吗？](#repeatCode)

## 什么是专有宿主机DDH？ {#concept .section}

阿里云专有宿主机（Dedicated Host，简称为DDH）是一台物理资源独享的云主机，物理服务器上的资源由一个租户独享，与其他租户在物理机级别上隔离。您能在DDH上创建ECS实例。更多信息，请参见 [什么是专有宿主机DDH](../../../../intl.zh-CN/产品简介/什么是专有宿主机DDH.md#)。

## DDH有什么优势？ {#features .section}

基于许可条款，您能将现有的许可证绑定到DDH上创建的ECS实例（包括但不限于Windows Server、Windows SQL Server），从而降低业务上云成本。DDH为您的应用部署提供了更大的灵活性、可见性和控制力，确保您的应用能满足更高等级的合规性和监管要求。更多信息，请参见 [产品优势](../../../../intl.zh-CN/产品简介/产品优势.md#)。

## 在什么场景下需要购买DDH？ {#scenarios .section}

DDH能满足一些特殊场景的需求，更多信息，请参见 [应用场景](../../../../intl.zh-CN/产品简介/应用场景.md#)。

## DDH是裸机产品吗？ {#bare .section}

不是。DDH上创建的ECS实例与您在共享宿主机上创建的ECS实例有相同的功能和特性。

## DDH与弹性裸金属服务器有什么区别？ {#ebm .section}

DDH是基于虚拟化技术的云服务器。弹性裸金属服务器（ECS Bare Metal Instance，简称为EBM）是一款同时兼具虚拟机弹性和物理机性能及特性的新型计算类产品，是基于阿里云完全自主研发的下一代虚拟化技术而打造的新型计算类服务器产品。关于EBM的信息，请参见 [弹性裸金属服务器（神龙）和超级计算集群（SCC）](../../../../intl.zh-CN/产品简介/实例/弹性裸金属服务器（神龙）和超级计算集群（SCC）.md#)。

## 怎么创建和释放DDH？ {#createAndRelease .section}

目前您只能通过 [ECS管理控制台](https://ecs.console.aliyun.com/#/home) 创建DDH。详细信息请参见 [创建DDH](../../../../intl.zh-CN/快速入门/创建DDH.md#)。预付费DDH到期一段时间后如果没有续费，则自动释放，详细信息请参见 [预付费](../../../../intl.zh-CN/产品定价/预付费.md#)。

## 怎么查看每台DDH上有多少可用资源？ {#viewAvailableResources .section}

每种规格的DDH的资源总量，请参见 [宿主机规格](../../../../intl.zh-CN/产品简介/宿主机规格.md#)。正在使用的DDH，您可以在 [ECS管理控制台](https://ecs.console.aliyun.com/#/home) 上查看剩余可用的资源，具体操作，请参见 [查看DDH的资源](../../../../intl.zh-CN/用户指南/查看DDH的资源.md#)。

## 能将共享宿主机上的ECS实例迁移到DDH上吗？ {#ecsMigrationEcs .section}

能。您能使用 [ECS管理控制台](https://ecs.console.aliyun.com/#/home) 将共享宿主机上的ECS实例迁移到同一账号下的DDH上。ECS实例重启之后就会部署在指定的DDH上。您不能迁移预付费ECS实例和竞价实例。具体操作，请参见 [将ECS实例从共享宿主机迁移到DDH](../../../../intl.zh-CN/用户指南/将ECS实例从共享宿主机迁移到DDH.md#)。

## 怎么在DDH上使用自带许可 \(BYOL\)？ {#byol .section}

按以下步骤操作：

1.  验证许可证条款是否支持在专有宿主机上使用您的软件许可。您可以向许可证顾问咨询。确认可以使用后，执行第2步。
2.  通过 [ECS管理控制台](https://ecs.console.aliyun.com/#/home) 或者 ImportImage 接口导入自定义镜像，或者远程连接ECS实例后直接下载软件。详细的接口信息，请参见 [远程连接ECS实例](../../../../intl.zh-CN/个人版快速入门/步骤 3：连接ECS实例.md#)。
3.  在DDH上启动使用了这些镜像的ECS实例。在运行这些实例时，您可能需要自己完成KMS授权激活实例或者软件。关于KMS的更多信息，请参见 密钥管理服务 文档。
4.  在DDH内使用BYOL许可证时，您可能需要向您的软件许可提供方递交审核表格。表格所需的DDH物理参数（比如CPU数量（Socket数）、物理CPU核数、vCPU核数等）能在ECS管理控制台上查看。

## DDH有唯一标识码吗？ {#code .section}

有。每台DDH都有一个机器码（类似于物理服务器的资产ID，非宿主机ID），您可以使用该机器码标识DDH。将DDH分配到您的账户时，机器码和物理服务器之间存在一一对应的关系，方便您备案资产。

## 阿里云会在不同的DDH上重复使用同一个机器码吗？ {#repeatCode .section}

不会。一个机器码只会用于一台物理服务器。如果您因为过保迁移等原因被分配了一台新的物理服务器，您的DDH会对应一个新的机器码，该机器码就是这台新物理服务器的唯一识别码。

