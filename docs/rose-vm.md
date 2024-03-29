# Ready-to-go Virtual Machine (rose-srv6)

The **rose-srv6** ready-to-go Virtual Machine is available for tutorial and development purposes
related to the [ROSE project](https://netgroup.github.io/rose/).

The rose-srv6 VM includes an emulated network environment based on Mininet and 
relies on the Linux kernel for implementing the SRv6 data plane.

In the control plane, the Linux nodes offer a gRPC southbound API to a controller
developed in python.

## SRv6 tutorials based on rose-srv6 VM

### ROSE-SRv6 tutorial on Linux - Part 1

- [Manual creation of SRv6 tunnels in the Linux SRv6 data plane](https://docs.google.com/document/d/18bVMeJ9SHgaFQwcIPgBOWBgP6ayUpyNNFNqRL0MhWgo/){:target="_blank"}

(used in the HPSR 2020 tutorial: [Segment Routing over IPv6 (SRV6) and the Network Programming Model](
https://hpsr2020.ieee-hpsr.org/program/tutorials/){:target="_blank"} and in the IEEE NFV-SDN tutorial: [SRv6 and the Network Programming Model Hands-On tutorial](https://nfvsdn2020.ieee-nfvsdn.org/program/tutorials/) ) 

### ROSE-SRv6 tutorial on Linux - Part 2

- [ROSE Control Plane : setting up SRv6 tunnels from the SDN controller](https://docs.google.com/document/d/1izO3H8dUt7VoemXtcH-RG4cL127tG9m48edOdFFmktU/){:target="_blank"}

(used in the IEEE NFV-SDN tutorial: [SRv6 and the Network Programming Model Hands-On tutorial](https://nfvsdn2020.ieee-nfvsdn.org/program/tutorials/) ) 


## How to install

The rose-srv6 VM is currently available for the Virtualbox hypervisor ([download](https://www.virtualbox.org/wiki/Downloads)) and for the VMware hypervisor.
For Virtualbox, we also support Vagrant ([download](https://www.vagrantup.com/downloads.html)) to manage the provisioning of the VM.

The rose-srv6 VM is used in the IEEE HPSR 2020 tutorial and in the IEEE NFV-SDN 2020, if you want to replicate the experiments during the hands-on part.
We invite you to subscribe to our [slack workspace](http://rose-slack.netgroup.uniroma2.it/) (channel #ieee-nfvsdn-tutorial)
for getting support about the rose-srv6 VM. See also our [contact page](https://netgroup.github.io/rose/rose-contacts.html).

The **password** for the *rose* user on the rose-srv6 VM is `1234`. To adapt the VM
to your keyboard layout see [below](#change-keyboard-layout).

### Virtualbox hypervisor 

#### Option 1. Direct download of .ova image for Virtualbox

We assume that you have installed the latest version of [Virtualbox](https://www.virtualbox.org/wiki/Downloads) (6.1). 

Download [rose-srv6-v2.7.ova](https://swift.cloud.garr.it/swift/v1/rose/vm/rose-srv6-v2.7.ova) (almost 4 GB).
<!-- http://rose-repo.netgroup.uniroma2.it/vm/rose-srv6.ova -->

Import *rose-srv6.ova* in Virtualbox (File-> Import Appliance)

#### Option 2. Deploy using Vagrant

We assume that you have installed the latest version of [Virtualbox](https://www.virtualbox.org/wiki/Downloads) (6.1) and [Vagrant](https://www.vagrantup.com/downloads.html) (2.2.7).

##### Option 2.1 Deploy the VM from the Vagrant Cloud

```
vagrant init rosevm/xubuntu
vagrant up
```

##### 2.2 Download the .box file from our repository

Download [rosevm-xubuntu-v2.7.box](https://swift.cloud.garr.it/swift/v1/rose/rosevm-xubuntu-v2.7.box) (almost 4 GB).
<!-- http://rose-repo.netgroup.uniroma2.it/vm/rosevm-xubuntu.box -->

Create a new directory rose-vm in your PC and move the file *rosevm-xubuntu.box* inside. 

Create a text file called "Vagrantfile" in the rose-vm directory, with this content:
[Vagrantfile](https://github.com/netgroup/rose-vm/raw/master/vagrant-from-box-file/Vagrantfile), then run:

```
cd rose-vm
vagrant up
```

### VMware hypervisor 

Download [rose-srv6-vmware-v2.7.ova](https://swift.cloud.garr.it/swift/v1/rose/vm/rose-srv6-vmware-v2.7.ova) (almost 4 GB).
<!-- http://rose-repo.netgroup.uniroma2.it/vm/rose-srv6-vmware.ova -->

Import the *rose-srv6-vmware.ova* as described [here](https://docs.vmware.com/en/VMware-Fusion/12/com.vmware.fusion.using.doc/GUID-275EF202-CF74-43BF-A9E9-351488E16030.html){:target="_blank"}.

## Advanced tips and tricks

### Change keyboard layout

1. Open the Settings Manager : Menu -> Settings -> Keyboard.
1. Switch to the Layout tab.
1. Uncheck Use system defaults.
1. Click the Add button and choose the appropriate keymap from the list.
1. **Remove the previous keymap**
1. Close the Settings Manager

### Rename the VM in option 2.1

In option 2.1, if you want to change the VM name to rose-srv6, edit the Vagrantfile auto-generated
after the first command, find the following line:

```
  config.vm.box = "rosevm/xubuntu"
```
add the following three lines immediately afterwards:

```
  config.vm.provider "virtualbox" do |v|
    v.name = "rose-srv6"
  end
```

### Scripted version of option 2.2 (for Linux)

```
git clone https://https://github.com/netgroup/rose-vm.git
cd rose-vm/vagrant-from-box-file
wget http://swift.cloud.garr.it/swift/v1/rose/vm/rosevm-xubuntu.box
vagrant up
```

### Using the Virtualbox rose-srv6 VM with VMware hypervisor

The Virtualbox rose-srv6 VM can also be used on VMware with some adaptation.
For using it with VMware you need to remove Virtualbox guest additions:

```
cd /opt/VBoxGuestAdditions-6.1.6/
sudo ./uninstall.sh
```

(I've followed [these instructions](https://askubuntu.com/questions/954376/removing-default-virtualbox-guest-additions)).

### List of github repositories

- [https://github.com/netgroup/rose-vm](https://github.com/netgroup/rose-vm)
- [https://github.com/netgroup/rose-vm-build](https://github.com/netgroup/rose-vm-build)
- [https://github.com/netgroup/rose-srv6-tutorial](https://github.com/netgroup/rose-srv6-tutorial)
- [https://github.com/netgroup/rose-dashboard](https://github.com/netgroup/rose-dashboard)
- [https://github.com/netgroup/rose-srv6-control-plane](https://github.com/netgroup/rose-srv6-control-plane)
- [https://github.com/netgroup/rose-srv6-pm-flask](https://github.com/netgroup/rose-srv6-pm-flask)
- [https://github.com/netgroup/rose-srv6-pm-dockerized](https://github.com/netgroup/rose-srv6-pm-dockerized)

### Github project board for developers' community

[rose-srv6 VM project board](https://github.com/orgs/netgroup/projects/2)


## Raw github version of this page (easier for working)

[https://github.com/netgroup/rose/blob/master/docs/rose-vm.md](https://github.com/netgroup/rose/blob/master/docs/rose-vm.md)

## github.io version of this page (nicer to read)

[https://netgroup.github.io/rose/rose-vm.html](https://netgroup.github.io/rose/rose-vm.html)

