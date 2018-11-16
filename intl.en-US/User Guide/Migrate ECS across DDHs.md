# Migrate ECS across DDHs {#task_vxp_3nn_tdb .task}

To meet your business requirements for flexible deployment, you can migrate ECS instances across DDHs under your account.

Before migrating an ECS instance across DDHs, make sure the following:

-   You have at least two DDHs of the same Dedicated Host type. For more information, see [create a DDH](../../../../intl.en-US/Quick Start/Create a DDH.md#).
-   The destination DDH has sufficient available resources for the ECS instance. For more information, see [view resources on a DDH](intl.en-US/User Guide/View resources on a DDH.md#).
-   The billing method of the ECS instance is supported on the destination DDH.

Before you migrate an ECS instance across DDHs, consider the following:

-   The source DDH and the destination DDH must be owned by one account, in the same region and zone, and of the same Dedicated Host type. However, ECS instances hosted on a DDH with local SSD disks cannot be migrated. For more information, see [dedicated host types](../../../../intl.en-US/Product Introduction/Dedicated Host types.md#).
-   The ECS instance must be in the **Stopped** status.

    **Note:** An ECS instance must be in the Stopped status when migrating. Stopping an ECS instance may interrupt your business operations. Proceed with caution.

-   The billing method of the ECS instance must be supported on the destination DDH:

    [Subscription](../../../../intl.en-US/Pricing/Subscription.md#) On a Subscription DDH, both Subscription and Pay-As-You-Go ECS instances can run. The Subscription ECS instance to be migrated must expire earlier than the destination DDH.


1.   Log on to the [ECS console](https://ecs.console.aliyun.com/#/home). 
2.   In the left-side navigation pane, click **Instances**. 
3.   Select a region. 
4.  In the upper-right corner of the instance list, click the settings icon, and on the dialog box, click **Dedicated Host**, and then click **OK**. You can view the **Dedicated Host** column in the table, which helps you locate the DDH that an ECS instance is hosted on.
5.   Find an ECS instance, and in the **Actions** column, select **More** \> **Stop**, to stop the instance. 
6.   When the instance is in the **Stopped** status, in the **Actions** column, select **More** \> **Modify DDH Deployment**. 
7.   On the dialog box, select a DDH and click **OK**. 

Refresh the instance list until the Dedicated Host information is updated. The instance starts automatically. Finally it is in the **Running** status.

