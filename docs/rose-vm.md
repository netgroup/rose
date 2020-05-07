# ROSE ready-to-go Virtual Machine (rose-srv6)

A ready-to-go Virtual Machine is available for tutorial and development purposes.

The rose-srv6 VM includes an emulated network environment based on Mininet and 
relies on the Linux kernel for implementing the SRv6 data plane.

In the control plane, the Linux nodes offer a gRPC southbound API to a controller
developed in python.

## How to install

The ROSE VM is currently available for the Virtualbox hypervisor ([download](https://www.virtualbox.org/wiki/Downloads)).
We also support Vagrant ([download](https://www.vagrantup.com/downloads.html)) to manage the provisioning of the VM.
 

### Option 1. Direct download of .ova image for Virtualbox

We assume that you have installed the latest version of [Virtualbox](https://www.virtualbox.org/wiki/Downloads). 

Download [rose-srv6.ova](http://swift.cloud.garr.it/swift/v1/rose/vm/rose-srv6.ova).

Import rose-srv6.ova in Virtualbox (File-> Import Appliance)

### Option 2. Deploy using Vagrant

We assume that you have installed the latest version of [Virtualbox](https://www.virtualbox.org/wiki/Downloads) and [Vagrant](https://www.vagrantup.com/downloads.html).

#### Option 2.1 Deploy the VM from the Vagrant Cloud

```
vagrant init rosevm/xubuntu
vagrant up
```

#### 2.2 Download the .box file from our repository

Create a new directory rose-vm in your PC. 

Download [rosevm-xubuntu.box](http://swift.cloud.garr.it/swift/v1/rose/vm/rosevm-xubuntu.box)
in the directory rose-vm.

Create a text file called "Vagrantfile" in the rose-vm directory, with this content:
[Vagrantfile](../vagrant-from-box-file/Vagrantfile), then run:

```
cd rose-vm
vagrant up
```

## Andvanced tips and tricks

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
