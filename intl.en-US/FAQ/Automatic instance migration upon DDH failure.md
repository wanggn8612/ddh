# Automatic instance migration upon DDH failure {#concept_xpn_4nn_tdb .concept}

A DDH is a physical server. It may shut down when a physical failure occurs. To prevent these failures from affecting your businesses, Alibaba Cloud supports automatic instance migration upon DDH failure.

**Warning:** You must use this function with caution because the migration deletes the data stored in local disks.

You can use the following methods to enable the automatic instance migration function. With this function enabled, when a DDH fails, the ECS instance running on the DDH will automatically migrate to another DDH.

-   Enable automatic instance migration when you create a DDH:

    Select **Automatic Instance Migration upon DDH Failure** under **DDH Settings**.

-   Enable automatic instance migration after you create a DDH:
    1.  Choose **Actions** \> **Edit DDH Info**.
    2.  Click the **Action on Maintenance** switch.

**Note:** A DDH configured with local disks, such as the local SSD i2 type, does not support the automatic instance migration function.

If the automatic instance migration function is disabled and your DDH fails, you must [submit a ticket](https://workorder-intl.console.aliyun.com/#/overview) to apply for a new DDH.

After the instance is migrated, the DDH ID and the metadata of the ECS instance remain unchanged. The metadata includes the ID, internal network IP address, and public network IP address of the ECS instance. The machine ID of the DDH is updated.

