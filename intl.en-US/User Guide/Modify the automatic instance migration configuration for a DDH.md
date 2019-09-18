# Modify the automatic instance migration configuration for a DDH {#task_388607 .task}

A Dedicated Host \(DDH\) is a physical server. It may be shut down when a physical failure occurs. To prevent these failures from affecting your business, Alibaba Cloud supports automatic instance migration upon DDH failure.

You can enable or disable this feature when or after you create a DDH.

-   For more information about how to configure automatic instance migration upon DDH failure when you create a DDH, see [Create a subscription DDH](../../../../intl.en-US/Quick Start/Create a subscription DDH.md#).
-   For more information about how to modify the configuration of automatic instance migration upon DDH failure after you create a DDH, see [Procedure](#all_steps).

**Note:** DDHs with local disks such as local SSD i2 do not support the automatic instance migration feature.

With the automatic instance migration feature enabled, if a DDH is shut down due to a failure, all Elastic Compute Service \(ECS\) instances that are running on the DDH are automatically migrated to a normal DDH. If the automatic instance migration feature is disabled and your DDH fails, you need to [open a ticket](https://workorder-intl.console.aliyun.com/#/overview) to apply for a new DDH.

**Note:** 

-   You must use this feature with caution because the migration deletes the data stored on local disks.
-   After all ECS instances of a faulty DDH are migrated to another DDH, the DDH ID and the metadata of the ECS instances remain unchanged on the destination DDH. The metadata includes the ID, private IP address, and public IP address of each ECS instance. The DDH machine ID is changed.

1.  Log on to the [ECS console](https://ecs.console.aliyun.com/#/ecs).
2.  In the left-side navigation pane, click **Dedicated Hosts**.
3.  Select the region of the target DDH.
4.  Modify the configuration of automatic instance migration. 
    1.  Select the target DDH.
    2.  Choose **Actions** \> **Edit DDH Info**.
    3.  In the Modify DDH Info dialog box, turn on or turn off the **Action On Maintenance** switch to enable or disable the automatic instance migration feature. As shown in the following figure, the automatic instance migration feature is disabled.

        ![feature_off](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/315040/156880150148146_en-US.png)

    4.  Click **Confirm**.

After modifying the automatic instance migration configuration, you can click **Details** in the **Operations** column of the target DDH to view the modification result on the **Details** tab.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/315040/156880150148151_en-US.png)

