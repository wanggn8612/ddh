# 修改DDH故障迁移配置 {#task_388607 .task}

专有宿主机DDH是一台物理服务器，可能会因为故障而自动停机。为了降低物理故障对您业务的影响，阿里云为您提供DDH故障迁移服务。

您可在创建DDH时或创建DDH后，开启或关闭故障迁移服务。

-   创建DDH时，配置故障迁移服务的步骤，请参见[创建DDH](../../../../cn.zh-CN/快速入门/创建DDH.md#)。
-   创建DDH后，修改DDH故障迁移配置的步骤，请参见[操作步骤](#all_steps)。

**说明：** 带有本地盘的专有宿主机（如本地SSD型 i2）不支持自动宕机迁移服务。

故障迁移服务开启后，当DDH因故障停机时，会自动迁移至健康的DDH。若您未开启DDH故障迁移服务，DDH发生故障停机后，您需要[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)申请置换一台健康的DDH。

**注意：** 

-   DDH因故障迁移后，本地盘数据会丢失。
-   DDH因故障迁移完成后，DDH ID及ECS实例的元数据（比如实例ID、私有IP地址、公网IP地址）均保持不变，但是由于物理机更换，DDH的机器码会改变。

1.  登录[ECS管理控制台](https://ecs.console.aliyun.com/#/ecs)。
2.  在导航栏左侧，单击**专有宿主机**。
3.  选择DDH所在地域。
4.  修改故障迁移配置。 
    1.  勾选需修改配置的DDH。
    2.  单击**操作** \> **修改主机信息**。
    3.  在修改宿主机信息对话框中，单击**自动宕机迁移**后面的按钮，开启或关闭该服务。 下图表示自动宕机迁移服务已关闭。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/315040/155917907048146_zh-CN.png)

    4.  单击**确定**。

修改自动宕机迁移配置后，您可在专有宿主机**操作**栏**详细信息** \> **宿主机信息**页面查看修改结果。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/315040/155917907048151_zh-CN.png)

