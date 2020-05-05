Segment Routing (SR) is a form of source routing. The SR architecture works by including a list of _segments_ in the packet headers. A segment can represent a _topological_ instruction (e.g. a node to be crossed) or a _service_ instruction (e.g. an operation to be executed on the packet). 

The Segment Routing architecture can be implemented using MPLS or IPv6 as data plane. We focus on the IPv6 implementation, called _SRv6_, in which the _segments_ are identified by IPv6 addresses. SRv6 supports advanced services like Traffic Engineering, Service Function Chaining and Virtual Private Networks in IPv6 backbones and datacenters. 

[We](#the-team) list our published papers [below](#scientific-papers) and present hereafter our open source _SRv6_ ecosystem, with a bottom up approach:   

[SREXT kernel module](#srext-kernel-module)

[SRNK SR proxy Native Kernel](#srnk---sr-proxy-native-kernel)

[pyroute2 extensions to support SRv6](#pyroute2-extensions-to-support-srv6)

[SRPerf performance evaluation for SRv6 implementations](#srperf---a-performance-evaluation-framework-for-srv6-implementations)

[SRv6 uSID (micro segment) implementation in Linux](#srv6-usid-micro-segment-implementation-in-linux)

[SRv6 uSID (micro segment) implementation on P4](#srv6-usid-micro-segment-implementation-on-p4)

[SRv6 PM - Performance Monitoring](#srv6-pm-srv6-performance-monitoring) 

[SRv6 SDN](#srv6-sdn)

[Emulation tools](#emulation-tools)

[Testbeds IntErconnections with L2 overlays – SRv6 for SFC](#testbeds-interconnections-with-l2-overlays--srv6-for-sfc)


### SREXT kernel module

[SREXT](https://netgroup.github.io/SRv6-net-prog/) is a kernel module providing the basic Segment Routing functions in addition to more advanced ones. It can be used as a standalone SRv6 implementation or as a complement to the existing SRv6 kernel implementation (kernel 4.10 and later kernels).

### SRNK - SR proxy Native Kernel

[SRNK](https://netgroup.github.io/srnk/) is an SR proxy which acts as relay mechanism in order to support SRv6 unaware VNFs. It is implemented extending the current support for SRv6 in Linux kernels (>= 4.14).

### pyroute2 extensions to support SRv6

[pyroute2](https://github.com/svinota/pyroute2) is a lightweight netlink library written in python. We submitted a patch which adds the support for _SRv6_ basic functionality.

Changelog:
- Introduce IPRoute support for SRv6 tunnel
- Add encap and inline modes
- Support hmac functionality for SRH
- Initial parsing of human friendly form
- Add seg6_encap_info for RTA_ENCAP mgmt

The extension is available from 0.5 release.

### SRPerf - a Performance Evaluation Framework for SRv6 implementations

[SRPerf](https://srouting.github.io/SRPerf/) is a performance evaluation framework for software and hardware implementations of SRv6.

### SRv6 uSID (micro segment) implementation in Linux

[This project](https://netgroup.github.io/srv6-usid-linux-kernel/) implements the SRv6 "micro segment"
(uSID for short) solution in Linux.

The processing of micro segments is performed by the Linux kernel, extending the existing SRv6 implementation. The iproute2 userspace tool has been modified to support the configuration of the SRv6 uSIDs.

### SRv6 uSID (micro segment) implementation on P4

[p4-srv6-usid](https://netgroup.github.io/p4-srv6-usid/) implements the SRv6 "micro segment"
(uSID for short) solution using the P4 language and shows a DEMO.

The SRv6 uSID solution is an extension to the SRv6 Network Programming model, which
allows expressing SRv6 segments with a very compact and efficient representation.

### SRv6-PM (SRv6 Performance monitoring)

[srv6-pm](https://netgroup.github.io/srv6-pm/) accurate Per-Flow Packet Loss Monitoring in Linux kernel

### SRv6 SDN

[SRv6 SDN](https://netgroup.github.io/srv6-sdn/) a collection of modules implementing different functionalities of a SDN controller for SRv6

### Emulation tools

The emulation tools are a collection of projects meant to support SRv6 experiments both over Mininet and IAAS like testbeds. Hereafter the list of projects composing our emulation tools:

- [RDCL 3D](https://github.com/superfluidity/RDCL3D) the webgui, it produces a json representation of the topology and allows the deployment and the control of the experiment
- [Dreamer Topology Parser and Validator](https://github.com/netgroup/Dreamer-Topology-Parser) is a library to parse the json representation of the topology
- [SRv6 Properties Generators](https://github.com/netgroup/srv6-properties-generators) is a library for the management of the addressing plan
- [SRv6 Mininet Extensions](https://github.com/netgroup/srv6-mininet-extensions) is a library to create Mininet networks for testing of SRv6 technology
- [SoftFire TIESR Deployer](https://github.com/netgroup/softfire-tiesr-deployer) creates the configuration of virtual networks for testing the SRv6 technology over IAAS like testbeds
- [SoftFire TIESR Scripts](https://github.com/netgroup/softfire-tiesr-scripts) these scripts are run over the VMs, they take into account the configuration files and consequently setup the VM

### Testbeds IntErconnections with L2 overlays – SRv6 for SFC 

The work concerns the deployment of arbitrary overlay topologies over multiple testbeds and the Service Function Chaining using SRv6 (IPv6 Segment Routing): “TIE-SR: Testbeds IntErconnections with L2 overlays – SRv6 for SFC” (see slides: <https://goo.gl/utvxzF>).

- **softfire-rdcl3d** the webgui, it produces a json representation of the topology it also offers a web URL to receive the notification from openbaton (TODO: Add the links to this repo)
- [Dreamer Topology Parser and Validator](https://github.com/netgroup/Dreamer-Topology-Parser) is a library to parse the json representation of the topology
- [SRv6 Properties Generators](https://github.com/netgroup/srv6-properties-generators) is a library for the management of the addressing plan
- [SoftFire TIESR Deployer](https://github.com/netgroup/softfire-tiesr-deployer) creates the configuration of virtual networks for testing the SRv6 technology over IAAS like testbeds
- [SoftFire TIESR Scripts](https://github.com/netgroup/softfire-tiesr-scripts) these scripts are run over the VMs, they take into account the configuration files and consequently setup the VM
- [SRv6 Controller](https://github.com/netgroup/srv6-controller) is a collection of modules implementing different functionalities of a SDN controller

### Videos 

TODO: Upload videos and add links

### VM images 

TODO: Upload image and add link

### Scientific papers 

- P. L. Ventre, M. M. Tajiki, S. Salsano, C. Filsfils,
"[SDN Architecture and Southbound APIs for IPv6 Segment Routing Enabled Wide Area Networks](https://arxiv.org/pdf/1810.06008.pdf)",
IEEE Transaction on Network and Service Management, Vol. 15, Issue 4, Dec 2018

- P. L. Ventre, S. Salsano, M. Polverini, A. Cianfrani, A. Abdelsalam, C. Filsfils, P. Camarillo, F. Clad,
"[Segment Routing: a Comprehensive Survey of Research Activities, Standardization Efforts and Implementation Results](https://arxiv.org/pdf/1904.03471)",
Submitted to a journal on June 2019, currently under review after first revision.

- A. Abdelsalam, P. L. Ventre, C. Scarpitta, A. Mayer, S. Salsano, P. Camarillo, F. Clad, C. Filsfils,
"[SRPerf: a Performance Evaluation Framework for IPv6 Segment Routing](https://arxiv.org/pdf/2001.06182)",
Submitted to a journal, currently under review.

- A. Mayer, S. Salsano, P. L. Ventre, A. Abdelsalam, L. Chiaraviglio, C. Filsfils,
"[An Efficient Linux Kernel Implementation of Service Function Chaining for legacy VNFs based on IPv6 Segment Routing](https://arxiv.org/pdf/1901.00936)",
5th IEEE International Conference on Network Softwarization (NetSoft 2019), 24-28 June 2019, Paris, France

- A. Mayer, E. Altomare, S. Salsano, F. Lo Presti, C. Filsfils,
"[The Network as a Computer with IPv6 Segment Routing: a Novel Distributed Processing Model for the Internet of Things](https://www.cse.wustl.edu/~cdgill/ngoscps2019/papers/NGOSCPS2019_Mayer_etal.pdf)",
NGOSCPS workshop at the CPS-IoT Week 2019, April 15 2019, Montreal, Canada (pdf)

- A. Abdelsalam, S. Salsano, F. Clad, P. Camarillo, C. Filsfils,
"[SR-Snort: IPv6 Segment Routing Aware IDS/IPS](http://netgroup.uniroma2.it/Stefano_Salsano/papers/18-sr-snort-demo.pdf)",
2018 IEEE Conference on Network Function Virtualization and Software Defined Networks – Demo Track – NFV-SDN’18, Verona, Italy, Nov 27-29, 2018

- A. Abdelsalam, P. L. Ventre, A. Mayer, S. Salsano, P. Camarillo, F. Clad, C. Filsfils,
"[Performance of IPv6 Segment Routing in Linux Kernel](http://netgroup.uniroma2.it/Stefano_Salsano/papers/18_srv6_perf_sr_sfc_workshop_2018.pdf)",
1st Workshop on Segment Routing and Service Function Chaining (SR+SFC 2018) at IEEE CNSM 2018, 5 Nov 2018, Rome, Italy (pdf)

- A. Abdelsalam, S. Salsano, F. Clad, P. Camarillo, C. Filsfils,
"[SERA: SEgment Routing Aware Firewall for Service Function Chaining scenarios](http://netgroup.uniroma2.it/Stefano_Salsano/papers/18-ifip-sera-firewall-sfc.pdf)",
IFIP Networking 2018 Conference (NETWORKING 2018), Zurich, Switzerland, May 14-16, 2018

- A. AbdelSalam, F. Clad, C. Filsfils, S. Salsano, G. Siracusano and L. Veltri  
"[Implementation of Virtual Network Function Chaining through Segment Routing in a Linux-based NFV Infrastructure](https://arxiv.org/pdf/1702.05157)",  
 3rd IEEE Conference on Network Softwarization (NetSoft 2017), Bologna, Italy, July 2017.

### The Team

- Stefano Salsano
- Ahmed Abdelsalsam
- Andrea Mayer
- Paolo Lungaroni
- Carmine Scarpitta
- Pier Luigi Ventre
- Pierpaolo Loreti
- Francesco Lombardo
- Mohammad M. Tajiki

[//]: # "see \cite{idsrarch}\cite{filsfils2015segment}"
[//]: # "# ROSE"
[//]: # "ROSE - Research on Open SRv6 Ecosystem, from Host Stack and APIs to Cloud Infrastructures"
