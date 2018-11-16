# Subscription {#concept_emw_lln_tdb .concept}

In this topic, you can learn about the payment methods supported by a Subscription Dedicated Host \(DDH\), the status of resources in different cases when a DDH expires, the renewal methods, viewing the bill, and the limits when using a Subscription DDH.

Subscription means paying for a DDH in advance for a specified term. According to the varied Billing Cycle, Subscription includes:

-   Pay-By-Year: The billing cycle is year.
-   Pay-By-Month: The billing cycle is month.

You can create Subscription or Pay-As-You-Go ECS instances on a Subscription DDH. For more information about the billing methods of ECS instances, see [pricing overview](../../../../intl.en-US/Pricing/Pricing overview.md#) of Elastic Compute Service \(ECS\).

## Payment Methods {#section_n5y_m25_tdb .section}

You can pay for a Subscription DDH by using the following methods:

-   Credit cards or PayPal account linked to your account. For more information about how to link a credit card or PayPal account to your Alibaba Cloud account, see [add a payment method](https://www.alibabacloud.com/help/zh/doc-detail/50517.html) in Account Management.
-   Coupons under your account that can be used to pay for Subscription products.

    **Note:** Log on to the [Billing Management](https://billing.console.aliyun.com/#/expense/outline) and go to **Coupon Management** page to view the **Applicable Scenarios** of your coupons and determine whether the coupons are applicable to Subscription products.


## Billing period {#section_q5y_m25_tdb .section}

Subscription DDHs are billed on a monthly, yearly or weekly basis. A billing cycle starts right from the second when DDH is purchased and ends at 00:00:00 \(UTC+8\) once the specified term of your purchase is fully used up. The billing cycle is based on the time of the UTC + 8 time zone.

**For example**: Hypothetically, you purchase a Subscription DDH at 13:23:56 on March 12, 2018, and pay for one-month use. The billing cycle ends at 00:00:00 on April 13, 2018.

## Price {#section_oyr_3kg_jfb .section}

The following table lists prices on a monthly basis for your reference only. For prices on a weekly or yearly basis, see the purchase page.

Unit: USD.

|DDH instance type|China North 1 \(Qingdao\)|China North 2 \(Beijing\)|China North 3 \(Zhangjiakou\)|China North 5 \(Huhehaote\)|China East 1 \(Hangzhou\)|China East 2 \(Shanghai\)|China South 1 \(Shenzhen\)|US West 1 \(Silicon Valley\)|US East 1 \(Virginia\)|Asia Pacific SE 1 \(Singapore\)|Hong Kong|Asia Pacific NE 1 \(Tokyo\)|US Central 1 \(Frankfurt\)|Middle East 1 \(Dubai\)|Asia Pacific SE 2 \(Sydney\)|Asia Pacific SE 3 \(Kuala Lumpur\)|Asia Pacific SOU 1 \(Mumbai\)|Asia Pacific SE 5 \(Jakarta\)|
|:----------------|:------------------------|:------------------------|:----------------------------|:--------------------------|:------------------------|:------------------------|:-------------------------|:---------------------------|:---------------------|:------------------------------|:--------|:--------------------------|:-------------------------|:----------------------|:---------------------------|:---------------------------------|:----------------------------|:----------------------------|
|sn1ne|954.09|954.09|858.68|858.68|954.09|954.09|954.09|1705.68|1264.21|1585.28|1585.28|1806.02|1557.79|1869.35|1685.62|1506.02|1294.83|1585.28|
|sn2ne|1346.00|1346.00|1346.00|1346.00|1346.00|1346.00|1346.00|1908.50|1449.06|1815.97|1815.97|2035.61|1914.25|2297.12|1963.25|1725.17|1397.47|1815.97|
|se1ne|1722.89|1722.89|1722.89|1722.89|1722.89|1722.89|1722.89|2334.46|2087.06|2516.05|2516.05|2481.97|2481.97|2978.37|2481.97|2390.26|1947.51|2516.05|
|c5|1362.26|1362.26|1226.04|1226.04|1362.26|1362.26|1362.26|2372.57|1758.49|2198.15|2198.15|2519.10|2198.15|2637.79|2198.15|2088.25|1891.11|2198.15|
|g5|2212.77|2212.77|2212.77|2212.77|2212.77|2212.77|2212.77|3004.99|2188.82|2745.30|2745.30|3079.19|2893.69|3472.44|2893.69|2608.05|2311.94|2745.30|
|r5|2707.39|2707.39|2707.39|2707.39|2707.39|2707.39|2707.39|3301.78|2967.89|3561.47|3561.47|3561.47|3561.47|4273.76|3561.47|3383.40|3042.74|3561.47|
|i2|3589.35|3589.35|3589.35|3589.35|3589.35|3589.35|3589.35|3600.96|3265.24|3905.88|3905.88|3784.00|3845.16|4614.28|3905.88|3710.96|3722.84|3905.88|

## DDH expires {#expire .section}

When an account is not overdue and an DDH is not renewed successfully within 15 days after expiration, the resources on the DDH cannot be used normally. when a DDH expires after a billing cycle, the status of the DDH and its ECS resources are shown as follows.

|Period|DDH|ECS Resources|
|:-----|:--|:------------|
|Within 15 days after the expiration day|Shut down.|Once DDH shuts down, its ECS instances stop automatically and the system disks and data disks become unavailable, but data on them is retained. ECS instances can be migrated to another Subscription DDH for use . For more information, see [migrate ECS instances across DDHs](../../../../intl.en-US/User Guide/Migrate ECS across DDHs.md#).|
|15 days after expiration|Released automatically.|Released automatically. All the data loss cannot be recovered.|

## Status changes after expiration {#section_cvy_m25_tdb .section}

After a Subscription DDH expires, the status of its resources varies according to whether [auto renewal](../../../../intl.en-US/User Guide/Auto renewal.md#) is enabled.

## Auto-renewal is disabled {#section_dvy_m25_tdb .section}

If the auto-renewal is disabled, the status of the Subscription DDH and its ECS resources change as follows.

|Period|DDH|ECS Resources|
|:-----|:--|:------------|
|Expiration Date|Shuts down automatically within the following 24 hours.|Once the DDH shuts down, its ECS instances stop automatically and the system disks and data disks become unavailable, but data on them is retained.|
|15 days after expiration|Released automatically.|Automatically released, all data is lost and cannot be recovered.|

## Auto-renewal is enabled {#section_gvy_m25_tdb .section}

If you have enabled auto-renewal, but a Subscription DDH is not renewed successfully after it expires, the status of the DDH and its ECS resources change as follows.

|Period|DDH|ECS Resources|
|:-----|:--|:------------|
|Within 15 days after expiration|Works normally.|Works normally.|
|15 days after expiration|Shuts down automatically within the following 24 hours.|Once the DDH shuts down, its ECS instances stop automatically and the system disks and data disks become unavailable, but data on them is retained.|
|30 days after expiration|Released automatically.|Released automatically. All data is lost and cannot be recovered.|

## Renewal {#section_kvy_m25_tdb .section}

After a billing cycle, you can perform [manual renewal](../../../../intl.en-US/User Guide/Manual renewal.md#).

Alternatively, you can enable [auto renewal](../../../../intl.en-US/User Guide/Auto renewal.md#) for a Subscription DDH. When this feature is enabled, Alibaba Cloud charges the subscription fee to your linked credit card or PayPal account on the expiration date \(T\). If the payment fails, Alibaba Cloud tries again on Day 7 \(T+6\) and Day 15 \(T+14\) until the payment is successful. If all the three payment attempts fail, the DDH shuts down.

## Conversion of billing methods {#section_lvy_m25_tdb .section}

Currently, conversion of billing methods of a DDH is not supported. However, you can convert the billing method of an ECS instance from Pay-As-You-Go to Subscription on a Subscription DDH. For more information, see [switch from Pay-As-You-Go to Subscription billing](../../../../intl.en-US/Pricing/Limits.md#).

## Limits {#section_mvy_m25_tdb .section}

Using a Subscription DDH has the following limits:

-   When you create a Subscription ECS instance on a Subscription DDH, the expiration time of the ECS instance cannot be later than that of the DDH.
-   When converting a Pay-As-You-Go ECS instance to a Subscription ECS instance, the expiration time of the instance cannot be later than that of the DDH.
-   A Subscription DDH is non-refundable.

## View bills {#section_pvy_m25_tdb .section}

Click **Bills** \> **Subscription** in the [Billing Management console](https://billing.console.aliyun.com/#/expense/outline) to view details of the Subscription DDH bills.

