# Auto renewal {#concept_t12_knn_tdb .concept}

When the auto renewal feature is enabled for a Subscription DDH, the DDH is renewed automatically according to the auto renewal schedule to avoid unexpected release.

## Fees deduction during auto renewal {#section_zcx_bbt_5db .section}

When the auto renewal feature is enabled, we charge the subscription fee to your linked credit card or PayPal account on the expiration date \(T\). If the payment fails, we will try again on Day 7 \(T+6\) and Day 15 \(T+14\) until the payment is successful. If all the three payment attempts fail, the DDH shuts down.

## Enable auto renewal {#section_adx_bbt_5db .section}

You can enable auto renewal by using either of the following methods.

**Enable on creation**

You can enable [create a DDH](../../../../intl.en-US/Quick Start/Create a DDH.md#) the auto renewal feature when creating a Subscription DDH.

When the feature is enabled, your Subscription DDH is renewed automatically, and the renewal period is determined by its purchase cycle:

-   For a yearly subscribed DDH, the renewal period is one year.
-   For a monthly subscribed DDH, the renewal period is one month.
-   For a weekly subscribed DDH, the renewal period is one week.

**Enable after creation**

After a Subscription DDH is created, you can enable the auto renewal feature in the ECS console. Below shows how to enable auto renewal feature after DDH creation.

The Subscription DDH is not in the **Expired** status.

To enable the auto renewal feature, follow these steps:

1.  Log on to the [ECS console](https://ecs.console.aliyun.com/#/home).
2.  In the left-side navigation pane, click **DDH**.
3.  Select a region.
4.  Select one or more Subscription DDHs. On the top of the table, select **Actions** \> **Set Auto Renewal**.
5.  In the dialog box, turn on the **Auto Renewal** switch, select a renewal period, and click **OK**.

## Disable auto renewal {#section_hdx_bbt_5db .section}

If you do not want your Subscription DDH to be renewed automatically, you can disable the feature.

To disable the auto renewal feature, follow these steps:

1.  Log on to the [ECS console](https://ecs.console.aliyun.com/#/home).
2.  In the left-side navigation pane, click **DDH**.
3.  Select a region.
4.  Select one or more Subscription DDHs. On the top of the table, select **Actions** \> **Set Auto Renewal**.
5.  In the dialog box, turn off the **Auto Renewal** switch. You can decide whether to turn on the **Do Not Renew** switch or not. When this switch is turned on, the DDH is not renewed after it expires.

