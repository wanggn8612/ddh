# Create an ECS instance on a DDH {#task_ihq_vmn_tdb .task}

You can create an ECS instance on a specified DDH, but only VPC-Connected ECS instances are supported.

Before you create an ECS instance on a specified DDH, complete the following:

-   [Create a DDH](intl.en-US/Quick Start/Create a DDH.md#).
-   [Register by using your real name](https://www.alibabacloud.com/help/zh/doc-detail/52595.htm) if you want to create an ECS instance in a region inside mainland China.
-   [Create a VPC and VSwitch](https://help.aliyun.com/document_detail/65430.html) in the region where the DDH is located.
-   If you do not want to use the default security group created by system, you must [Create a security group](https://help.aliyun.com/document_detail/25468.html) and [Add security group rules](https://help.aliyun.com/document_detail/25471.html). For more information, see [Default security group rules](https://help.aliyun.com/document_detail/31707.html).
-   [Create an SSH key pair](https://help.aliyun.com/document_detail/51793.html) for creating a Linux instance authenticated by using a key pair.
-   Write the [User-defined data](https://help.aliyun.com/document_detail/49121.html) for customizing the startup behaviors of an instance or passing in user-defined data.
-   [Create an instance RAM role and grant permissions to authorize an instance to play a role](https://help.aliyun.com/document_detail/61175.html) .

You can create an ECS instance on a specified DDH. Only VPC-Connected ECS instances are supported. The functional differences between the ECS instance on a DDH and that on a shared cloud hosting server, see [Comparing ECS features on different hosts](../../../../intl.en-US/Product Introduction/Comparing ECS features on different hosts.md#).

1.   Log on to the [ECS Console](https://ecs.console.aliyun.com/#/home). 
2.   In the left-side navigation pane, click **Dedicated Hosts**. 
3.   Select a region. 
4.   Select a DDH and click **Create Instance** to start creating an ECS instance on the DDH. 
5.   Follow these steps to complete **Basic Configurations**: 
    1.   select a **Dedicated Host**: Use the selected DDH that is displayed by default. Alternatively, you can select another DDH. 
    2.   select a **Billing Method**: The billing method of an ECS instance is determined by the DDH. 

        On a Subscription DDH, both **Subscription** and **Pay-As-You-Go** ECS instances are supported.

    3.   Confirm **Region**: The region and zone of the ECS instance is determined by the selected DDH. 
    4.   Select an ECS instance type and specify the instance quantity. The eligible ECS instance type is determined by the selected type and available resources of the DDH. For more information, see [Dedicated Host types](../../../../intl.en-US/Product Introduction/Dedicated Host types.md#). 
    5.   You can select a public image, custom image, shared image, or marketplace image. 

        **Note:** 

        -   To use an SSH key pair, select a Linux OS image.
        -   To use user-defined data, select an image listed in User-defined data. For more information, see [Create an instance RAM role and grant permissions to authorize an instance to play a role](https://help.aliyun.com/document_detail/61175.html) .
    6.   Select Storage: 
        -   **System Disk**: Required. A system disk is required for the image. Specify the cloud disk category and size for the system disk:
            -   Cloud disk category: You can select any cloud disk category in the selected region.
            -   Size: The default size range is \[40, 500\] GiB. If the selected image is greater than 40 GiB, the default size range is \[ImageSize, 500\] GiB. The available size range varies according to the selected image, as shown in the following table.

                |Operating System|System disk capacity|
                |:---------------|:-------------------|
                |Linux \(excluding CoreOS\) FreeBSD|\[max\{20, ImageSize\}, 500\] GiB In the public image list, only Ubuntu 14.04 32-bit, Ubuntu 16.04 32-bit, and CentOS 6.8 32-bit are of 40 GiB size.|
                |CoreOS|\[max\{30, ImageSize\}, 500\] GiB|
                |Windows| \[max\{40, ImageSize\}, 500\] GiB|

        -   **Data Disk**: Optional. To add data disks now, specify the category, size, and quantity of data disks, and **encrypt** the disks or not. You can create an empty data disk or create a data disk from a snapshot. Up to 16 data disks can be added.

            **Note:** The data disks added here have the following features:

            -   The data disks added here have the same billing method with that of the instance.
            -   A Subscription data disk is released along with the instance, and a Pay-As-You-Go data disk can be set to be released along with the instance.
        -   If you have selected an instance type that has local disks, such as instance type of the i2 family, the local storage information is displayed. You cannot modify the quantity or category of local storage, which is determined by the selected instance type. For more information, see [Instance type families](../../../../intl.en-US/Product Introduction/Instance type families.md#) of Elastic Compute Service \(ECS\).
6.   Click **Next: Networking** to complete the networking and security group configuration: 
    1.  Select Network: Use the default **VPC \(Virtual Private Cloud\)**. You must select a VPC and a VSwitch. If you do not have a VPC and a VSwitch, you can use the default ones.
    2.  Configure the Internet bandwidth:
        -   To assign a public IP address to the instance, select **Assign public IP**, select **PayByTraffic** and specify a bandwidth value. You cannot unbind the assigned public IP address from the instance. For more information about network billing, see [Billing of network bandwidth](../../../../intl.en-US/Pricing/Billing of network bandwidth.md#).
        -   To use elastic public IP \(EIP\) address for Internet access, do not select **Assign public IP**.
    3.  Select a security group: All the rules must meet your business operation needs.

        **Note:** You can use the default security group and add rules by yourself. For more information, see [Default security group rules](https://help.aliyun.com/document_detail/31707.html).

    4.  Add an elastic network interface. If your selected instance type supports elastic network interfaces, you can add one and specify a VSwitch for it.

        **Note:** By default, the elastic network interface is released along with the instance. You can use the ECS console or the [DetachNetworkInterface](https://help.aliyun.com/document_detail/58514.html) interface to detach network interface from the instance

7.   Click **Next: System Configurations** to complete the following configurations: 
    -   Select and set Log on Credentials. You can set it now or select **Set Later** to set the credential after the instance is created. Select a credential based on the image:
        -   Linux: You can select a password or SSH key pair as a logon credential.
        -   Windows: You can only select a password as a logon credential.
    -   Specify the instance name, which is displayed in the ECS console, and the host name, which is displayed inside the guest operating system.
    -   Set Advanced configurations:
        -   Instance RAM role: Assign a RAM role to the instance.
        -   User-defined data: Customize the startup behaviors of an instance or pass data into an instance.
8.   Click **Next: Grouping**. 

    If you have multiple instances, you can add tags to the instance to simplify future management.

9.   Confirm the order: 
    -   In the **Configurations Selected** area, confirm all the configurations. You can change configurations by clicking ![](images/1347_en-US.png) the Edit configurations icon.
    -   To create a **Pay-As-You-Go** instance, you can set **Auto Release Schedule**
    -   To create a **Subscription** instance, you can specify the Purchase cycle and select **Auto-Renew**.

        **Note:** The expiration time of a Subscription ECS instance cannot be later than that of the selected DDH.

    -   Confirm Instance Cost. It is the sum of the cost of the system disk, the data disks \(if any\), and public traffic.
    -   Read and confirm ECS Service Terms and Product Terms of Service.
10.  Click **Create Order**。 

After the instance is created, click **ECS Console** to go back to the ECS console to view the created ECS instance. In the **Instance** page, you can view the instance ID, the public IP address, and the private IP address of the new created instance. By setting the **Set Display Items**, you can view the Dedicated Host where the instance is hosted in the instance list.

**Note:** For more information about   **Set Display Items**, see [Migrate ECS across DDHs](../../../../intl.en-US/User Guide/Migrate ECS across DDHs.md#).

-   You can create an FTP site on the instance for transferring files. For more information, see [Build an FTP site on an ECS instance](https://help.aliyun.com/document_detail/51998.html).
-   To secure your instance after creation, we recommend that you perform security compliance inspection and configuration:
    -   Linux instances: See Harden operating system security for Linuxin [Security Advisories](https://help.aliyun.com/document_detail/49809.html).
    -   Windows instances: See Harden operating system security for Windows in [Security Advisories](https://help.aliyun.com/document_detail/49781.html).
-   If a data disk is created along with the instance, you must partition the disk and format the partitions. If the instance is based on a Linux OS, see [Format and mount a data disk](https://help.aliyun.com/document_detail/25426.html). If the instance is based on a Windows OS, see [Format a data disk](https://help.aliyun.com/document_detail/25418.html).

