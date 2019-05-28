# Create a DDH {#task_fbz_5mn_tdb .task}

Learn how to create a DDH in the ECS console.

-   [Sign up with Alibaba Cloud](https://www.alibabacloud.com/help/doc-detail/50482.htm).
-   [Add a payment method](https://www.alibabacloud.com/help/doc-detail/50517.htm).

You can create a DDH in the ECS console.

**Note:** We are testing the beta Dedicated Host. You can [open a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex) to apply for a trial.

1.  Log on to the [ECS console](https://ecs.console.aliyun.com/#/home).
2.  In the left-side navigation pane, click **Dedicated Hosts**.
3.  On the Dedicated Host list page, click **Create Dedicated Host**.
4.  On the Create page, complete the following configurations: 
    1.  **Billing Method**: Select **Subscription**.
    2.  **Region**: How to select a region, see [regions and zones](../../../../intl.en-US/General Reference/Regions and zones.md#).
    3.  Select a **Dedicated Host Type**, type a valid **Dedicated Host Name**, and specify the quantity. For more information, see [dedicated host types](../../../../intl.en-US/Product Introduction/Dedicated Host types.md#). 

        **Note:** When selecting a Dedicated Host type, consider the following:

        -   The selected Dedicated Host type determines the configurations of the ECS instances hosted on the DDH.
        -   The ECS instances cannot be migrated across DDHs with local SSD disks.
    4.  To create a Subscription DDH, select a **Purchase cycle** and determine whether to turn on the **Auto renewal switch** or not.
    5.  Confirm **Dedicated Host Service Terms**.
    6.  Confirm the costs.
    7.  Click **Create Order**.
5.  On the **Create Order** dialog box, confirm the configurations and click **OK**.
6.  To create a Subscription DDH, make payment to activate the service by following the prompts.

Go back to the Dedicated Hosts page to view the new DDH. It may take several minutes to create a DDH. Refresh the page if you cannot see it. The DDH is ready to use when it is in the **Running** status.

Follow-up operations:

-   [Create an ECS instance on a DDH](intl.en-US/Quick Start/Create an ECS instance on a DDH.md#).
-   [Migrate ECS from a shared cloud hosting server to a DDH](../../../../intl.en-US/User Guide/Migrate ECS from a shared cloud hosting server to a DDH.md#).

