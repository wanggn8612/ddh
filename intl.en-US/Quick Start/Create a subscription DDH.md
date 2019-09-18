# Create a subscription DDH {#task_fbz_5mn_tdb .task}

This topic describes how to create a subscription Dedicated Host \(DDH\) in the Elastic Compute Service \(ECS\) console.

-   [An Alibaba Cloud account is registered](https://www.alibabacloud.com/help/doc-detail/50482.htm).
-   [A credit card or PayPal account is bound to your Alibaba Cloud account](https://www.alibabacloud.com/help/doc-detail/50517.htm).

1.  Log on to the [ECS console](https://ecs.console.aliyun.com/#/ddh/region/cn-beijing).
2.  In the left-side navigation pane, click **Dedicated Hosts**.
3.  On the Dedicated Hosts page, click **Create DDH**.
4.  On the DDH creation page that appears, specify the following configuration: 
    1.  **Billing Method**: Select **Subscription**.
    2.  **Region**: Select the region of the DDH. For example, to create a DDH in Beijing, select China \(Beijing\). For more information about the regions and zones, see [Regions and zones](../../../../intl.en-US/General Reference/Regions and zones.md#).
    3.  Set **Dedicated Host Type** and **DDH Name**, and specify the quantity. For more information about the supported DDH types, see [Dedicated host types](../../../../intl.en-US/Product Introduction/Dedicated host types.md#).

        **Note:** When selecting a DDH type, note the following information:

        -   The selected DDH type determines the type family and quantity of the ECS instances that can be run on the DDH.
        -   ECS instances cannot be migrated between DDHs with local SSDs.
    4.  **DDH Settings**: Select **Automatic Instance Migration upon DDH Failure** as required. This check box is selected by default. Select **Set UDP Session Timeout Period** as required. With the automatic instance migration feature enabled, if a DDH is shut down due to a failure, the instances running on the DDH are automatically migrated to a normal DDH. You can modify the configuration after creating the DDH. For more information, see [Modify the automatic instance migration configuration for a DDH](../../../../intl.en-US/.md#).

        **Note:** DDHs with local disks such as local SSD i2 do not support the automatic instance migration feature.

    5.  Set **Duration** and select **Auto-Renew** as required.
    6.  After reading and confirming the terms of service, select **Dedicated Host Terms of Service**.
    7.  Confirm the cost.
    8.  Click **Preview**.
5.  In the **Preview** dialog box that appears, confirm the configuration and click **Create Order**.
6.  Pay for the order as prompted.

Go back to the Dedicated Hosts page. The created DDH appears in the list. It may take several minutes to create a DDH. Refresh the page if you cannot find the created DDH in the list. When the status of the DDH is **Running**, you can start to use the DDH.

You can perform the following operations:

-   [Create an ECS instance on a DDH](intl.en-US/Quick Start/Create an ECS instance on a DDH.md#)
-   [Migrate ECS from a shared cloud hosting server to a DDH](../../../../intl.en-US/User Guide/Migrate ECS from a shared cloud hosting server to a DDH.md#)

