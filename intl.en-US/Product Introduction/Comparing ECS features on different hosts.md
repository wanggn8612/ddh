# Comparing ECS features on different hosts {#concept_wwk_jkn_tdb .concept}

ECS instances running on a DDH and a shared hosting server have differences.

The differences between ECS instances running on a DDH and a shared hosting server are listed in the following table.

|Item|ECS on shared cloud hosting|ECS on Dedicated Hosts|
|:---|:--------------------------|:---------------------|
|Network Type|VPC and classic network. For more information, see [network types](../../../../intl.en-US/Network/Network types.md#).|VPC|
|Chargeable resources|See [pricing overview](../../../../intl.en-US/Pricing/Pricing overview.md#).|For more information, see [billing of ECS resources on a DDH](../../../../intl.en-US/Pricing/Billing of ECS resources on a DDH.md#).|
|Billing methods| Subscription, Pay-As-You-Go, and Spot instances

 | Subscription

 |
|Renewal period|Set the renewal period according to your business needs.|After renewal, the ECS instance must expire earlier than the DDH. For more information, see [limits](intl.en-US/Product Introduction/Limits.md#).|
|No fees for stopped instances \(VPC-Connected\)|For more information, see [no fees for stopped VPC instances](../../../../intl.en-US/Pricing/No fees for stopped VPC instances.md#).|In the Stop Instance, No Fees mode, the computing resources, including vCPU and memory, are retained, but other ECS resources keep being charged. For more information, see [billing of ECS resources on a DDH](../../../../intl.en-US/Pricing/Billing of ECS resources on a DDH.md#)|
|Pay-As-You-Go to Subscription| For more information, see [switch from Pay-As-You-Go to Subscription billing](../../../../intl.en-US/Pricing/Switch from Pay-As-You-Go to Subscription billing.md#), the function limit conditions must be met

 |Besides all the limitations of the feature, only ECS instances running on a Subscription DDH supports this feature, and after conversion, the expiration time of an ECS instance cannot be later than that of a DDH.|
|ECS instance type|For more information, see [what is ECS](../../../../intl.en-US/Product Introduction/What is ECS?.md#).|Determined by the Dedicated Host types. For more information, see [dedicated host types](intl.en-US/Product Introduction/Dedicated Host types.md#)|
|Create an ECS instance|For more information, see [create an instance](../../../../intl.en-US/Quick Start for Entry-Level Users/Step 2. Create an instance.md#).|For more information, see [create an ECS instance on a DDH](../../../../intl.en-US/Quick Start/Create an ECS instance on a DDH.md#).|
|Change instance configurations|For more information, see [upgrade or downgrade instance configurations](../../../../intl.en-US/Instances/Change configurations/Overview of configuration changes.md#ChangeType)|Not supported.|
|Adjust the Internet bandwidth|For more information, see [adjust Internet bandwidth](../../../../intl.en-US/Instances/Change configurations/Overview of configuration changes.md#ChangeBandwidth).|For more information, see [adjust Internet bandwidth](../../../../intl.en-US/Instances/Change configurations/Overview of configuration changes.md#ChangeBandwidth). **Note:** You cannot change the configurations of a Subscription instance while adjusting the Internet bandwidth.

 |
|Assign a public IP address|For more information, see [assign a public IP address](../../../../intl.en-US/Instances/Change configurations/Overview of configuration changes.md#AllocatePublicIp).|For more information, see [assign a public IP address](../../../../intl.en-US/Instances/Change configurations/Overview of configuration changes.md#AllocatePublicIp). **Note:** You cannot change the configurations of a Subscription instance while adjusting the Internet bandwidth.

 |
|Release an ECS instance| -   Pay-As-You-Go instances can be released automatically or manually. For more information, see [release an instance](../../../../intl.en-US/Instances/Manage instances/Release an instance.md#).
-   When a Subscription ECS instance expires or a Pay-As-You-Go ECS instance is out of service because of payment overdue, it is released automatically.

 |When a Subscription DDH expires and is not renewed, the ECS instances hosted on it are released automatically.|

