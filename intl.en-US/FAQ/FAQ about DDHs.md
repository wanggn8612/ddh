# FAQ about DDHs {#concept_b2q_mnn_tdb .concept}

-   [What is Dedicated Host \(DDH\)?](#)
-   [What are the benefits of using DDH?](#)
-   [In what scenarios do I use a DDH?](#)
-   [Is a DDH a bare-metal server?](#)
-   [What is the difference between DDHs and ECS Bare Metal Instances?](#)
-   [How can I create a DDH?](#)
-   [How can I view the available resources on a DDH?](#)
-   [Can I migrate an ECS instance from shared cloud hosting to a DDH?](#)
-   [How can I use my own licenses on a DDH?](#)
-   [Does a DDH have a unique identification code?](#)
-   [Do different DDHs share one machine serial number?](#)

## What is Dedicated Host \(DDH\)? {#concept .section}

Dedicated Host, abbreviated to DDH, is a physical server provided by Alibaba Cloud. You can have a full control over the physical resources of the server. Resources are isolated on physical server level. You can create ECS instances on a DDH. For more information, see [what is a dedicated host](../../../../intl.en-US/Product Introduction/What is a Dedicated Host.md#).

## What are the benefits of using DDH? {#features .section}

DDH allows you to use existing software licenses, including Windows Server and Windows SQL Server. Subject to your license terms, you can bind your own software licenses to your ECS instances on a DDH, which brings down the cost of migrating your business to cloud. DDH facilitates higher flexibility, visibility, and controllability. All these features trigger your business to meet higher level regulatory compliance requirements. For more information, see [benefits](../../../../intl.en-US/Product Introduction/Benefits.md#).

## In what scenarios do I use a DDH? {#scenarios .section}

For more information, see [scenarios](../../../../intl.en-US/Product Introduction/Scenarios.md#).

## Is a DDH a bare-metal server? {#bare .section}

No. ECS instances on DDHs have the same features with those on shared cloud hosting servers.

## What is the difference between DDHs and ECS Bare Metal Instances? {#ebm .section}

A DDH is a cloud server with Alibaba Cloud hypervisor deployed. ECS Bare Metal \(EBM\) Instance is a new type of computing product that features both elasticity of virtual machines and performance and has characteristics of physical machines. As a product completely and independently developed by Alibaba Cloud, EBM instances are based on the next-generation virtualization technology. For more information about EBM instances, see [ECS Bare Metal Instance and Super Computing Clusters](../../../../intl.en-US/Product Introduction/Instances/ECS Bare Metal Instance and Super Computing Clusters.md#).

## How can I create a DDH? {#createAndRelease .section}

Currently, you can create a DDH in the [ECS console](https://ecs.console.aliyun.com/#/home). For more information, see [create a DDH](../../../../intl.en-US/Quick Start/Create a DDH.md#). Pre-paid DDH is released automatically if there is no volume after a period of expiration. For more information, see [Subscription](../../../../intl.en-US/Pricing/Subscription.md#).

## How can I view the available resources on a DDH? {#viewAvailableResources .section}

The Dedicated Host types article lists the total resources of each available DDH type, see [dedicated host types](../../../../intl.en-US/Product Introduction/Dedicated Host types.md#). If you are using a DDH, log on to the [ECS console](https://ecs.console.aliyun.com/#/home) to view the available resources on the DDH. For more information, see [view resources on a DDH](../../../../intl.en-US/User Guide/View resources on a DDH.md#).

## Can I migrate an ECS instance from shared cloud hosting to a DDH? {#ecsMigrationEcs .section}

Yes. Log on to the [ECS console](https://ecs.console.aliyun.com/#/home) and migrate an ECS instance from shared cloud hosting to one of your DDHs. The migration takes effect after you restart the ECS instance. You cannot migrate Subscription ECS instances or spot instances. For more information, see [migrate ECS from a shared cloud hosting server to a DDH](../../../../intl.en-US/User Guide/Migrate ECS from a shared cloud hosting server to a DDH.md#).

## How can I use my own licenses on a DDH? {#byol .section}

Follow these steps:

1.  Verify that the license can be used on a dedicated host. Y You can check it with your license consultant. If it can be used on a dedicated host, go to step 2.
2.  Import a custom image in the [ECS console](https://ecs.console.aliyun.com/#/home) or by using the ImportImage interface. Alternatively, connect to the ECS instance and download the software. For detailed interface information, see [connect to an ECS instance](../../../../intl.en-US/Quick Start for Entry-Level Users/Step 3: Connect to an instance.md#).
3.  Start the ECS instances that are running the custom image. You may have to activate KMS service before you start the ECS instances. For more information about KMS, see Key Management Service
4.  When using the Bring-Your-Own-License \(BYOL\) licenses, you may have to apply for permission. You can find all the physical attributes of the DDH in the ECS console, including the number of sockets, physical CPU cores, and virtual CPU cores.

## Does a DDH have a unique identification code? {#code .section}

Yes. Each DDH has a unique machine serial number, not the host ID displayed in the ECS console. The number works as an asset ID of the physical server. You can use it to identify a DDH and record the DDH as an asset.

## Do different DDHs share one machine serial number? {#repeatCode .section}

No. One machine serial number is assigned to one physical server. If you are assigned a new physical server because the earlier one is out of warranty, you will get a new machine serial number, which is the unique identifier of the new server.

