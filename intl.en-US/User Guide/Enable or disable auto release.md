# Enable or disable auto release {#concept_dvl_lnn_tdb .concept}

You can enable the Auto Release feature to schedule the release of a Pay-As-You-Go DDH to avoid any unnecessary charges.

Only Pay-As-You-Go DDHs can be released automatically.

**Warning:** When the **Auto Release** feature is enabled, all the ECS instances located on a Pay-As-You-Go DDH are released along with the DDH. Proceed with cautions.

**Note:** To release a Pay-As-You-Go DDH immediately, see [Release a DDH](../../../../intl.en-US/Quick Start/Release a DDH.md#).

## Enable auto release {#section_vnp_rft_5db .section}

To enable auto release, follow these steps:

1.  Log on to the [ECS console](https://ecs.console.aliyun.com/#/home).
2.  In the left-side navigation pane, click **DDH**.
3.  Select a region.
4.  Select one or more DDHs, on the top of the table, select **Actions** \> **Release**.
5.  In the dialog box, select **Auto Release**. Click **OK**after completing these steps:
    1.  Turn on the **Auto Release** switch.
    2.  Set **Release Date** and **Release Time**. The system will not allow the DDH to be released, if the auto release schedule time is set within 30 minutes from the current time.

        ![](images/1352_en-US.png)


## Disable auto release {#section_uxf_2gt_5db .section}

Follow these steps to disable auto release:

1.  Log on to the [ECS console](https://ecs.console.aliyun.com/#/home).
2.  In the left-side navigation pane, click **DDH**.
3.  Select a region.
4.  Select one or more DDHs, on the top of the table, select **Actions** \> **Release**.
5.  In the dialog box, select **Auto Release**, turn off the **Auto Release** switch, and then click **OK**.

