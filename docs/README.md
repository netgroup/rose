Segment Routing (SR) is a form of source routing. The SR architecture works by including a list of _segments_ in the packet headers. A segment can represent a _topological_ instruction (e.g. a node to be crossed) or a _service_ instruction (e.g. an operation to be executed on the packet). 

The Segment Routing architecture can be implemented using MPLS or IPv6 as data plane. We focus on the IPv6 implementation, called _SRv6_, in which the _segments_ are identified by IPv6 addresses. SRv6 supports advanced services like Traffic Engineering, Service Function Chaining and Virtual Private Networks in IPv6 backbones and datacenters. 

With a bottom up approach, [we](#the-team) present hereafter our open source _SRv6_ ecosystem:

[SREXT kernel module](#srext-kernel-module)

[SRNK SR proxy Native Kernel](#srnk)

[pyroute2 extensions to support SRv6](#pyroute2-extensions-to-support-srv6)

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
- Introduces IPRoute support for SRv6 tunnel
- Adds encap and inline modes
- Supports hmac functionality for SRH
- Initial parsing of human friendly form
- Add seg6_encap_info for RTA_ENCAP mgmt

The extension is available from 0.5 release.

### SRv6-PM (SRv6 Performance monitoring)

[srv6-pm](https://netgroup.github.io/srv6-pm/) We have implemented accurate Per-Flow Packet Loss Monitoring in Linux kernel

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

TODO: Add the links to these repo:

- **softfire-rdcl3d** the webgui, it produces a json representation of the topology it also offers a web URL to receive the notification from openbaton
- [Dreamer Topology Parser and Validator](https://github.com/netgroup/Dreamer-Topology-Parser) is a library to parse the json representation of the topology
- [SRv6 Properties Generators](https://github.com/netgroup/srv6-properties-generators) is a library for the management of the addressing plan
- [SoftFire TIESR Deployer](https://github.com/netgroup/softfire-tiesr-deployer) creates the configuration of virtual networks for testing the SRv6 technology over IAAS like testbeds
- [SoftFire TIESR Scripts](https://github.com/netgroup/softfire-tiesr-scripts) these scripts are run over the VMs, they take into account the configuration files and consequently setup the VM
- [SRv6 Controller](https://github.com/netgroup/srv6-controller) is a collection of modules implementing different functionalities of a SDN controller

### Videos 

TODO: Upload videos and add links

### VM image 

TODO: Upload image and add link

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
