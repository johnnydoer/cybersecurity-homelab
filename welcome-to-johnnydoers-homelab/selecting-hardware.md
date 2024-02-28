---
description: Criteria when selecting hardware before procurement.
---

# Selecting Hardware

My current homelab setup consists of 3 PCs, all with different configurations, that I was able to find on Facebook Marketplace for some good deals.

Let me first start with the specifications of the hardware that I have and then I will explain what features I was looking for when selecting my hardware.

<details>

<summary>My Homelab Hardware</summary>

* &#x20;<mark style="color:purple;">**Proxmox Server 1**</mark>
  * _**CPU:**_ AMD FX-6300 | 6 Cores 6 Threads 95 W 3.5 GHz
  * _**GPU:**_ NVIDIA GeForce GTX 960 2 GB
  * _**RAM:**_ 22GB DDR3
    * 2x 8GiB - 933MHz
    * 1x 4GiB - 800MHz
    * 1x 2 GiB - 800MHz
  * _**SSD:**_ ADATA SU630 240GB
  * _**HDD:**_ 4x Seagate BarraCuda 4TB 5.4K 6.0Gb/s
  * _**PSU:**_ Seasonic 620W 80 Plus Bronze
  * _**MBD:**_ GIGABYTE GA-970A-DS3P (rev 2.x)
  * _**NET:**_ D-Link DGE-530T 10/100/1000 Gigabit Desktop Adapter

<!---->

* <mark style="color:purple;">**Proxmox Server 2**</mark>
  * _**CPU:**_ AMD FX-6300 | 6 Cores 6 Threads 95 W 3.5 GHz
  * _**GPU:**_&#x20;
    * AMD Radeon RX 570
    * NVIDIA GeForce GTX 1060 6GB
  * _**RAM:**_ 16GB DDR3
    * 2x 4GiB - 933MHz
    * 2x 4GiB - 800MHz
  * _**SSD:**_ Intel SSD 540s 240GB
  * _**HDD:**_ Seagate Constellation ES.3  2TB 7.2K 6.0Gbps
  * _**PSU:**_ EPower 800W
  * _**MBD:**_ GIGABYTE GA-970A-UD3P (rev 2.x)
  * _**NET:**_ Realtek RTL8169/8110 Family PCI Gigabit Ethernet NIC

<!---->

*   <mark style="color:purple;">**Proxmox Server 3**</mark>

    * _**CPU:**_ Intel Core i7-6700 | 8 Cores 8 Threads 65 W 4 GHz
    * _**GPU:**_
      * GeForce GTX 1060 6GB
      * GeForce RTX 2060 6 GB Rev. A
    * _**RAM:**_ 16GB DDR4
      * 2x 8GiB - 1913MHz
    * _**SSD:**_ Samsung 860 EVO 500GB
    * _**HDD:**_ Seagate Constellation ES.3  2TB 7.2K 6.0Gbps
    * _**PSU:**_ SilverStone 850W 80 Plus Gold
    * _**MBD:**_ ASUS Z170-A
    * _**NET:**_ Realtek RTL8169/8110 Family PCI Gigabit Ethernet NIC


* Router
  * Linksys EA8500 Max-Stream™ AC2600 MU-MIMO Smart Wi-Fi Router

</details>

So the things that I was looking for when selecting the above hardware was:

* Processor (CPU):
  * Support for virtualization.
    * In AMD Processors: Definition AMD Virtualization (<mark style="color:red;">AMD-V</mark>)
    * In Intel Processors: Intel® Virtualization Technology (<mark style="color:red;">VT-x</mark>)
  * Support for IOMMU:
    * In AMD Processors: AMD's I/O Virtualization Technology (<mark style="color:red;">AMD-Vi</mark>)
    * In Intel Processors: Intel® Virtualization Technology for Directed I/O (<mark style="color:red;">VT-d</mark>)
  * As low Power Draw (TDP) as possible.
* Motherboard (MBD):
  * Support for IOMMU: Check [here](https://en.wikipedia.org/wiki/List\_of\_IOMMU-supporting\_hardware#Motherboards\_2) or in the original documentation of the motherboard.
* Memory:
  * More RAM > Faster RAM (uptil a limit for both).
  * Prefer RAM capacity till 64 GB (or your limit, depending on your use case) and if you still have budget left then you can get that 64 GB RAM with faster speeds.
* Storage:
  * Solid State Drives (SSD) for operating systems.
  * Hard Disk Drives (HDD) for storing media/other data if you cannot afford all SSDs.
* Graphics Cards:
  * Depends on budget and use case, for me, I wanted to try some machine learning/large language models on my VMs.
* Network Cards:
  * Required for router/firewall purposes, minimum 1 Gbit/s.
  * Prefer PCI over PCIe if using PCIe lanes for other devices (such as GPUs).
* Router (Optional)
  * One that is supported by OpenWrt. Check [here](https://openwrt.org/toh/start).



Now, that we have the hardware ready, in the next page let's look at the architecture of the setup.
