# FAQ about ECS instances on DDH {#concept_pzj_nnn_tdb .concept}

-   [What is the difference between ECS instances on a DDH and on a shared cloud hosting server?](#comparison)
-   [Are there any limits to creating ECS instances on a DDH?](#limits)
-   [Can any type of ECS instances be created on a DDH?](#ecsInstance)
-   [Can ECS instances be created on a specified DDH?](#createEcsInstance)
-   [Can I migrate ECS instances between different DDHs?](#ecsMigrationDdh)

## What is the difference between ECS instances on a DDH and on a shared cloud hosting server? {#comparison .section}

The only difference is that you cannot create classic network-connected ECS instances on DDHs. For more information, see [Comparing ECS features on different hosts](../../../../intl.en-US/Product Introduction/Comparing ECS features on different hosts.md#).

Performance: basically the same. However, you have a full control over the physical resources of a DDH.

## Are there any limits to creating ECS instances on a DDH? {#limits .section}

You cannot create classic network-connected ECS instances on a DDH, and the billing method of ECS instances has dependencies on the corresponding DDH. For more information, see [Limits](../../../../intl.en-US/Product Introduction/Limits.md#).

## Can any type of ECS instances be created on a DDH? {#ecsInstance .section}

Yes. You can create an ECS instance on a specified DDH in the ECS console or by using the CreateInstance interface of ECS. For example, you can only create ECS instances of sn1ne type family on a DDH of compute optimized type with enhanced network performance. For more information about DDH type, see [Dedicated Host types](../../../../intl.en-US/Product Introduction/Dedicated Host types.md#).

## Can ECS instances be created on a specified DDH? {#createEcsInstance .section}

Yes. You can create ECS instances on a specified DDH in the ECS Console. For more information, see [Create an ECS instance on a DDH](../../../../intl.en-US/Quick Start/Create an ECS instance on a DDH.md#).

## Can I migrate ECS instances between different DDHs? {#ecsMigrationDdh .section}

Yes. You can migrate ECS instances between DDHs of the same type, except DDHs with local disks. For more information, see [Migrate ECS across DDHs](../../../../intl.en-US/User Guide/Migrate ECS across DDHs.md#).

