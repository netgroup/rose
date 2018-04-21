Segment Routing (SR) is a form of source routing. The SR architecture works by including a list of _segments_ in the packet headers. A segment can represent a _topological_ instruction (e.g. a node to be crossed) or a _service_ instruction (e.g. an operation to be executed on the packet). 

The Segment Routing architecture can be implemented using MPLS or IPv6 as data plane. We focus on the IPv6 implementation, called _SRv6_, in which the _segments_ are identified by IPv6 addresses. SRv6 supports advanced services like Traffic Engineering, Service Function Chaining and Virtual Private Networks in IPv6 backbones and datacenters. 

[SREXT kernel module](#srext-kernel-module)

[SRv6 SDN Architecture and Southbound APIs](#srv6-sdn-architecture-and-southbound-apis)

[Testbeds IntErconnections with L2 overlays – SRv6 for SFC](#testbeds-interconnections-with-l2-overlays–srv6-for-sfc)

[pyroute2 extensions to support SRv6](#pyroute2-extensions-to-support-srv6)

[The Team](#the-team)

### SREXT kernel module

[SREXT](https://netgroup.github.io/SRv6-net-prog/) is a kernel module providing the basic Segment Routing functions in addition to more advanced ones. It can be used as a standalone SRv6 implementation or as a complement to the existing SRv6 kernel implementation (kernel 4.10 and later kernels).

### SRv6 SDN Architecture and Southbound APIs

TODO: Add the links to repos of the Southbound APIs libraries in the Controller and to the modules in the SRv6 node

### Testbeds IntErconnections with L2 overlays – SRv6 for SFC 

The work concerns the deployment of arbitrary overlay topologies over multiple testbeds and the Service Function Chaining using SRv6 (IPv6 Segment Routing): “TIE-SR: Testbeds IntErconnections with L2 overlays – SRv6 for SFC” (see slides: https://goo.gl/utvxzF).

TODO: Add the links to these repos: 

-  **test-rdcl** the webgui, it produces a json representation of the topology it also offers a web URL to receive the notification from openbaton
- **dreamer-topology-parser-and-validator** it is a library to parse the json representation of the topology
- **softfire-tiesr-deployer** it produces the configuration files to setup the VMs, in particular to
    create the vxlan tunnels
- **softfire-tiesr-scripts** these scripts are run over the VMs, they take into account the
    configuration files and consequently setup the VM

### pyroute2 extensions to support SRv6

patch: https://github.com/svinota/pyroute2/commit/dd8cb44033ead2d65d73ad288cf45be0fbfeee50
Features:
- Introduces IPRoute support for SRv6 tunnel
- Adds encap and inline modes
- Supports hmac functionality for SRH
- Initial parsing of human friendly form
- Add seg6_encap_info for RTA_ENCAP mgmt

Available on github https://github.com/svinota/pyroute2

### The Team

- Ahmed Abdelsalsam
- Pier Luigi Ventre
- Mohammad M. Tajiki
- Stefano Salsano

[//]: # "see \cite{idsrarch}\cite{filsfils2015segment}"
[//]: # "# rose"
[//]: # "ROSE - Research on Open SRv6 Ecosystem, from Host Stack and APIs to Cloud Infrastructures"
