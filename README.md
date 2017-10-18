# Enabling-Agile-Adaptation-in-Dense-Heterogeneous-Deployments-of-Commercial-802.11-Devices 
## AGILE System 
In this demonstration, we aim at showcasing the advanced adaptation capabilities of the AGILE
system on top of commercial 802.11ac compatible hardware. The developed system builds on the
open-source ath10k driver for 802.11ac chipsets of Qualcomm to deliver an abstraction of open
and reconfigurable PHY layer. Our development provides an API enabling real-time reconfiguration
of key operational parameters, such as channel central frequency per available wireless interface at
the access-point (AP) side and channel bandwidth per connected client. Moreover, the API enables
controlled band steering and client roaming capabilities, enabling efficient transferring of clients
between the available interfaces of dual-band APs or even among multiple in-range APs belonging to
the same network.

Building on top of the developed API exposing an open and reconfigurable PHY layer, the AGILE
system also brings intelligent adaptation algorithms. Taking advantage of the inherent spectrum
sensing capabilities of COTS 802.11 equipment, AGILE implements an accurate mechanism for
quantifying spectrum occupancy, as impacted jointly by spectrum sharing and interference. The
impact of common interference sources, such as co-channel 802.11 transmissions, cross-technology
emissions (MW ovens, LTE-U, IoT devices) and even 802.11 impairments, such as “hidden-terminals”,
can be characterized through a unified approach with minimal overhead. The outcome of the
spectrum occupancy evaluation process is used to identify under-utilized spectrum fragments and
drive efficient spectrum adaptation decisions (channel frequency and bandwidth) per AP interface
through the underlying reconfigurable PHY layer.

In an effort to drive network-wide efficient resource allocation, AGILE also introduces a central
controller entity that collects statistics from all in-network APs. Local agents run on each AP, as
background services over the OpenWRT embedded Linux, to continuously estimate the link
quality and traffic demand per client and also monitor the available channel airtime per AP interface.
Information collected locally is fed to the central controller, where intelligent adaptation decisions
are applied. Based on the collected link quality information per client, local controllers running at the
APs enable identification of low-SNR links, which can be efficiently mitigated through bandwidth
reduction and/or steering of clients using 5 GHz links to the 2.4 GHz band. In addition, network-wide
traffic load information is exploited to detect performance bottlenecks that are dynamically handled
by the controller through efficient distribution of available wireless capacity, by performing
transparent to the end-users band steering and client roaming. Through the developed mechanism
the overall network is able to dynamically adapt to varying channel and traffic conditions.

![Alt text](https://user-images.githubusercontent.com/24733570/31709158-6cfa87e6-b3f1-11e7-9b58-20272b1762ed.jpg)

> Further details can be found in the published paper: http://nitlab.inf.uth.gr/NITlab/papers/Spectrum_ICC_submit.pdf
