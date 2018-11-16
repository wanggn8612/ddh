# Life cycle of DDH {#concept_qvm_fkn_tdb .concept}

This topic describes all the statuses of a DDH from its creation to its release.

A life cycle of a DDH starts right from its creation and ends with its release. The following table displays the various statuses of a DDH.

|Status|Attribute|Description|Visible in the console|
|:-----|:--------|:----------|:---------------------|
|Starting|Transitory|A DDH is in the status before Running during its time of creation. If a DDH is in this status for a long time, an exception occurs.|Yes|
|Running|Stable|The DDH is running properly. You can create and manage ECS instances on a DDH in such a status.|Yes|
|Error|Stable| An error occurs to the DDH. You can [open a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex) to report and solve the problem.

 |Yes|
|Expired|Stable| DDH falls in this status, when a Subscription DDH expires. You must renew the subscribed DDH. With this action, the status changes from **Expired** to Running. For more information about renewal, see [manual renewal](../../../../intl.en-US/User Guide/Manual renewal.md#).

 |Yes|
|Released|Stable|When a [Subscription](../../../../intl.en-US/Pricing/Subscription.md#) DDH is released because of expiration, it enters this status. When a DDH is released, all its resources become unavailable.|No|

