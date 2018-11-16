# Pay-As-You-Go {#concept_u5g_4ln_tdb .concept}

In this topic, you can learn about the activation, payment methods, deduction rules ,resource status changes and the limits of a Pay-As-You-Go Dedicated Host \(DDH\).

Pay-As-You-Go means paying for a DDH on the actual period of use, on a per second basis. A Pay-As-You-Go DDH is settled on an hourly basis.

On a Pay-As-You-Go DDH, you cannot create subscription instances but can create ECS instances only. For more information about the billing rules of Pay-As-You-Go ECS instances, see [pricing overview](../../../../intl.en-US/Pricing/Pricing overview.md#).

## Activation {#section_j2h_xx5_tdb .section}

Have permission to create Pay-As-You-Go DDH. Contact your account manager to apply to create a Pay-As-You-Go DDH.

## Payment Methods {#section_l2h_xx5_tdb .section}

You can use a credit card or a PayPal account to pay for a DDH of the Pay-As-You-Go billing method. You must link them to your account. For more information, see [add a payment method](https://www.alibabacloud.com/help/doc-detail/50517.html).

**Note:** IIf PayPal is used, after you activate a Pay-As-You-Go DDH and place an order, Alibaba Cloud preauthorizes your PayPal account first.

## Period of use {#section_n2h_xx5_tdb .section}

A Pay-As-You-Go DDH is billed for actual period of use. It is billed on a per second basis. Billing starts once it is created. However, it shuts down either when you [release a DDH](../../../../intl.en-US/Quick Start/Release a DDH.md#) or if the payment is overdue. The minimum charge for the life cycle of a DDH \(from creation to release\) is USD 0.01.

## Settlement {#section_o2h_xx5_tdb .section}

A Pay-As-You-Go DDH is settled on an hourly basis. For settlement, consider the following:

-   Payments for Pay-As-You-Go DDHs are settled with other products under your account that follow Pay-As-You-Go billing method.
-   If your account has overdue bills, settlement of other orders may fail, or the system may deduct the balance for the overdue bills before settling other orders.
-   Generally, if the cumulative monthly consumption amount of your account is less than 1,000 USD, fees are deducted on the first day of the following month.
-   If you have a quota agreement with Alibaba Cloud, fees are deducted when the cumulative consumption amount of your account exceeds the quota.


|Cumulative consumption amount|Due date \(T\)|Fee deduction day|Description|
|:----------------------------|:-------------|:----------------|:----------|
|Cumulative monthly consumption amount less than 1,000 USD.|The first day of the following month.|T, T+7, and T+14| -   In the event of deduction failure on the due date \(T\), fees are deducted again on the day T+7 and the day T+14.
-   If all the three payment deduction attempts fail, the DDH shuts down and is rendered out of service on day T+15. In this case, its ECS instances stop running but the data is retained. Billing stops when the instance is out of service.
-   When the DDH is out of service, [open a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex) to clear the overdue payment. After the overdue payment is cleared, the DDH is running again.
-   If the overdue payment cannot be cleared until the day T+30, the DDH is released and data cannot be recovered.

 |
|Agreed quota|On the day when the quota is exceeded|

## Conversion of billing methods {#section_y2h_xx5_tdb .section}

Currently, you cannot convert the billing method of a DDH from Pay-As-You-Go to Subscription. For more information about Subscription billing rules, see [Subscription](intl.en-US/Pricing/Subscription.md#).

## Limits {#section_z2h_xx5_tdb .section}

Using a Pay-As-You-Go DDH has the following limits:

-   Only Pay-As-You-Go ECS instances can be created on a Pay-As-You-Go DDH.

-   A Pay-As-You-Go ECS instance on it cannot be converted to a Subscription ECS instance.


## View bills {#section_bfh_xx5_tdb .section}

Log on to the [Billing Management console](https://billing.console.aliyun.com/#/expense/outline) to view details of the Pay-As-You-Go DDH bills.

-   Go to **Bills \>** \> **Pay-As-You-Go** page to get the paid details of a Pay-As-You-Go DDH.
-   Go to **Bills \>** \> **Unsettled** page to get the unpaid details of a Pay-As-You-Go DDH.

## View usage {#section_cfh_xx5_tdb .section}

Click **Usage Records** in the [Billing Management console](https://billing.console.aliyun.com/#/expense/outline) to view the detailed usage records of a Pay-As-You-Go DDH. Exports detailed usage records for the Pay-As-You-Go DDH.

