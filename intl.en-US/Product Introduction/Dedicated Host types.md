# Dedicated Host types {#concept_h3g_zzm_tdb .concept}

A Dedicated Host type determines the ECS instance type family and the number of ECS instances that you can create on a DDH.

A Dedicated Host type is determined on the basis of a scenario, which defines the configurations of physical cores, sockets, memory, and local disks of a DDH. A Dedicated Host type is determined on the basis of a scenario which is used by ECS instance type family on a sharing host. You can create ECS instances of the permitted type family on a DDH and flexibly combine the different instance types until its resources are used out. For example, on a DDH of compute optimized type with enhanced network performance, you can create ECS instances of all sn1ne types. For more information about ECS instance type family, see Elastic Compute Service \(ECS\). For all the ECS instances running on a DDH, make sure that the packet forwarding rate and the bandwidth capacity of the DDH are not exceeded. Network performance for each instance type, see [Instance type families](../../../../intl.en-US/Product Introduction/Instance type families.md#).

Currently, the available Dedicated Host types are shown in the following table.

|**Dedicated Host type**|Compute optimized type with enhanced network performance|General-purpose type with enhanced network performance|Memory optimized type with enhanced network performance|General-purpose type|Compute type|Memory type|Local SSD disks type|
|**ECS instance type family**|sn1ne|sn2ne|se1ne|g5|c5|r5|i2|
|**Number of CPUs \(Socket\)**|2|2|2|2|2|2|2|
|**Physical CPU model \(2.5 GHz\)**|Intel Xeon E5-2682 v4 \(Broadwell\)|Intel Xeon E5-2682 v4 \(Broadwell\)|Intel Xeon E5-2682 v4 \(Broadwell\)|Xeon Platinum 8163 \(Skylake\)|Xeon Platinum 8163 \(Skylake\)|Xeon Platinum 8163 \(Skylake\)|Xeon Platinum 8163 \(Skylake\)|
|**Physical CPU cores**|32|32|32|48|48|48|48|
|**vCPU cores\***[\*](#)|56|56|56|84|86|86|80|
|**Memory \(GiB\)**|112|35|448|336|172|688|640|
|**Local SSD disk \(GiB\)**[\*\*](#)|N/A|N/A|N/A|N/A|N/A|N/A|17880|
|**Bandwidth \( Gbit/s\)**[\*\*\*](#)|10 |10 | 10|25|25|25|25|
|**Packet forwarding rate \(Thousand pps\)**[\*\*\*](#)|4,500|4,500|4,500|550|550|550|550|

\*vCPU cores = physical CPU cores \* 2－vCPU cores reserved by the host

\*\*For more information about local SSD disks, see [Local disks](../../../../intl.en-US/Product Introduction/Block storage/Local disks.md#) in the ECS Product Introduction.

\*\*\* For all the ECS instances running on a DDH, make sure that the packet forwarding rate and the bandwidth capacity of the DDH are not exceeded. Network performance for each instance type, see [Instance type families](../../../../intl.en-US/Product Introduction/Instance type families.md#).

