# Limits {#concept_gjy_gkn_tdb .concept}

DDHs have the following limits.

**Note:** If you are using an ECS instance on a DDH, besides the following limits, you must also consider the limits to ECS. For more information, see [limit](../../../../intl.en-US/User Guide/Limits.md#) of Elastic Compute Service \(ECS\).

|Item|Limit|Supply for higher configuration or unlock configuration rights|
|:---|:----|:-------------------------------------------------------------|
|Permission to create a DDH| Complete [real-name registration](https://www.alibabacloud.com/help/doc-detail/52595.htm) to create a DDH in the mainland China regions.

 |Not supported.|
|Supported network types|Virtual Private Cloud \(VPC\). For more information about VPC, see [what is VPC](../../../../intl.en-US/Product Introduction/What is VPC?.md#).|Not supported.|
|Billing methods links between a DDH and its ECS instances| Subscription DDH: For both Pay-As-You-Go and Subscription ECS instances.

 |Not supported.|
| Configurations of Subscription ECS instances on a Subscription DDH

 |The expiration time of the ECS instance cannot be later than that of the DDH.|Not supported.|
| Auto-renewal Subscription ECS instances on a Subscription DDH

 |The expiration of the ECS instance after auto-renewal cannot be later than that of DDH. If the time for auto-renewal is against the rule, auto-renewal fails.|Not supported.|
|[Conversion of billing methods](../../../../intl.en-US/Pricing/Limits.md#) of ECS instances on a DDH| Available for the Pay-As-You-Go ECS instances on a Subscription DDH. After conversion, the expiration time of an ECS instance cannot be later than that of a DDH.

 |Not supported.|
|Conversion of billing methods of a DDH|Not supported.|Not supported.|
|ECS instance migration between shared cloud hosting and DDH| Only Pay-As-You-Go ECS instances can be migrated. Subscription ECS instances and Preemptible instances cannot be migrated.

 |Not supported.|
|ECS instance migration between DDHs|Instances can be migrated only between DDHs of the same [dedicated host type](intl.en-US/Product Introduction/Dedicated Host types.md#) under one account. ECS instances on a DDH with local SSD disks cannot be migrated.|Not supported.|

