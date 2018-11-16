# Billing of ECS resources on a DDH. {#concept_qrv_tmn_tdb .concept}

You can learn the billing rules of the ECS resources when running ECS instances on a DDH.

For the ECS instances hosted on a DDH, you are not billed for using vCPU, memory, and local disks. However, you must pay for chargeable images, cloud disks, and network bandwidth.

For more information about the billing rules of these ECS related resources, see [Subscription](../../../../intl.en-US/Pricing/Subscription.md#), [billing of network bandwidth](../../../../intl.en-US/Pricing/Billing of network bandwidth.md#), and [Pay-As-You-Go billing](../../../../intl.en-US/Pricing/Pay-As-You-Go billing.md#).

When the Pre-paid DDH does not expire or, there are different resource billing scenarios associated with the ECS instance that are running in different States.

## Running ECS instances {#section_drm_rcw_tdb .section}

When an ECS instance hosted on a DDH is in the **Running** status, all the ECS related resources are charged.

## Stopped ECS instances {#section_erm_rcw_tdb .section}

When an ECS instance hosted on a DDH is in the Stopped status, billing of the ECS related resources varies according to the billing method of the instance.

-   Subscription ECS instances

    After a Subscription ECS instance is stopped, the billing continues for all the ECS related resources.

-   Pay-As-You-Go ECS instances

    The [no fees for stopped VPC instances](../../../../intl.en-US/Pricing/No fees for stopped VPC instances.md#) feature does not apply to the ECS instances hosted on a DDH. When an instance is stopped, all its ECS related resources are billed as follows:

    -   Image: Retained. Billing continues for a chargeable image.
    -   Network bandwidth:
        -   If the instance is assigned with a public IP address, the IP address will be released, and you do not get billed for network bandwidth.
        -   If an EIP address is bound to the instance, the EIP address is retained, and billing continues for holding the EIP address and the network bandwidth.

            **Note:** When an ECS instance is stopped, its private IP address is retained.

    -   Cloud disks: Retained. Billing continues for the cloud disks.

