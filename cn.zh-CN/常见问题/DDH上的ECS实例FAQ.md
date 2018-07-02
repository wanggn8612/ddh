# DDH上的ECS实例FAQ {#concept_pzj_nnn_tdb .concept}

-   [在DDH和共享宿主机上创建的ECS实例有什么区别？](#comparison)
-   [在DDH上创建ECS实例有什么限制吗？](#limits)
-   [能在同一台DDH上创建不同规格的ECS实例吗？](#ecsInstance)
-   [能指定一台DDH创建ECS实例吗？](#createEcsInstance)
-   [能在不同的DDH之间迁移ECS实例吗？](#ecsMigrationDdh)

## 在DDH和共享宿主机上创建的ECS实例有什么区别？ {#comparison .section}

功能方面：DDH不支持创建经典网络ECS实例。其他功能差异，请参见 [ECS实例功能对比](../../../../cn.zh-CN/产品简介/ECS实例功能对比.md#)。

性能方面：基本一致。但是DDH是单租户环境，DDH所在物理服务器由您独享。

## 在DDH上创建ECS实例有什么限制吗？ {#limits .section}

DDH上不能创建经典网络类型的ECS实例。DDH的计费方式会限制能创建的ECS实例，详细信息，请参见 [使用限制](../../../../cn.zh-CN/产品简介/使用限制.md#)。

## 能在同一台DDH上创建不同规格的ECS实例吗？ {#ecsInstance .section}

能。只要DDH资源容量允许，您能在一台DDH上创建主机规格支持的任何规格的ECS实例。比如，在一台计算网络增强型规格的DDH上，您能创建所有sn1ne规格的ECS实例，但是不能创建其他规格族ECS实例。详细的DDH规格信息，请参见 [宿主机规格](../../../../cn.zh-CN/产品简介/宿主机规格.md#)。

## 能指定一台DDH创建ECS实例吗？ {#createEcsInstance .section}

能。您能通过ECS管理控制台在指定的DDH上创建ECS实例。详细信息，请参见 [在DDH上创建ECS实例](../../../../cn.zh-CN/快速入门/在DDH上创建ECS实例.md#)。

## 能在不同的DDH之间迁移ECS实例吗？ {#ecsMigrationDdh .section}

能。您能在同一账号下相同主机规格的DDH之间迁移ECS实例，但是不包括本地SSD型DDH。具体操作，请参见 [在不同DDH之间迁移ECS实例](../../../../cn.zh-CN/用户指南/在不同DDH之间迁移ECS实例.md#)。

