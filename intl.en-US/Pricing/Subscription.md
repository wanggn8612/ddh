# Subscription {#concept_emw_lln_tdb .concept}

In this topic, you can learn about the payment methods supported by a Subscription Dedicated Host \(DDH\), the status of resources in different cases when a DDH expires, the renewal methods, viewing the bill, and the limits when using a Subscription DDH.

Subscription means paying for a DDH in advance for a specified term. According to the varied Billing Cycle, Subscription includes:

-   Pay-By-Year: The billing cycle is year.
-   Pay-By-Month: The billing cycle is month.

You can create or Pay-As-You-Go ECS instances on a Subscription DDH. For more information about the billing methods of ECS instances, see [pricing overview](../../../../reseller.en-US/Pricing/Billing overview.md#) of *Elastic Compute Service \(ECS\)* .

## Payment Methods {#section_n5y_m25_tdb .section}

## Billing period {#section_q5y_m25_tdb .section}

Subscription DDHs are billed on a monthly, yearly or weekly basis. A billing cycle starts right from the second when DDH is purchased and ends at 00:00:00 \(UTC+8\) once the specified term of your purchase is fully used up. The billing cycle is based on the time of the UTC + 8 time zone.

**For example**: Hypothetically, you purchase a Subscription DDH at 13:23:56 on March 12, 2018, and pay for one-month use. The billing cycle ends at 00:00:00 on April 13, 2018.

## Price {#section_oyr_3kg_jfb .section}

The following table lists prices on a monthly basis for your reference only. For prices on a weekly or yearly basis, see the purchase page.

## DDH expires {#expire .section}

When an account is not overdue and an DDH is not renewed successfully within 15 days after expiration, the resources on the DDH cannot be used normally. when a DDH expires after a billing cycle, the status of the DDH and its ECS resources are shown as follows.

|Period|DDH|ECS Resources|
|:-----|:--|:------------|
|Within 15 days after the expiration day|Shut down.|Once DDH shuts down, its ECS instances stop automatically and the system disks and data disks become unavailable, but data on them is retained. ECS instances can be migrated to another Subscription DDH for use . For more information, see [migrate ECS instances across DDHs](../../../../reseller.en-US/User Guide/Migrate ECS across DDHs.md#).|
|15 days after expiration|Released automatically.|Released automatically. All the data loss cannot be recovered.|

## Status changes after expiration {#section_cvy_m25_tdb .section}

After a Subscription DDH expires, the status of its resources varies according to whether [auto renewal](../../../../reseller.en-US/User Guide/Auto renewal.md#) is enabled.

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

After a billing cycle, you can perform [manual renewal](../../../../reseller.en-US/User Guide/Manual renewal.md#).

## Conversion of billing methods {#section_lvy_m25_tdb .section}

Currently, conversion of billing methods of a DDH is not supported. However, you can convert the billing method of an ECS instance from Pay-As-You-Go to Subscription on a Subscription DDH. For more information, see [switch from Pay-As-You-Go to Subscription billing](../../../../reseller.en-US/Pricing/Switch from Pay-As-You-Go to Subscription billing.md#).

## Limits {#section_mvy_m25_tdb .section}

Using a Subscription DDH has the following limits:


## View bills {#section_pvy_m25_tdb .section}

