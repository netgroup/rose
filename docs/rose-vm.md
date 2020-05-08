# Ready-to-go Virtual Machine (rose-srv6)

The **rose-srv6** ready-to-go Virtual Machine is available for tutorial and development purposes
related to the [ROSE project](https://netgroup.github.io/rose/).

The rose-srv6 VM includes an emulated network environment based on Mininet and 
relies on the Linux kernel for implementing the SRv6 data plane.

In the control plane, the Linux nodes offer a gRPC southbound API to a controller
developed in python.

## How to install

The rose-srv6 VM is currently available for the Virtualbox hypervisor ([download](https://www.virtualbox.org/wiki/Downloads)).
We also support Vagrant ([download](https://www.vagrantup.com/downloads.html)) to manage the provisioning of the VM.

The rose-srv6 VM will be used in the IEEE HPSR tutorial, if you want to replicate the experiments during the hands-on part.
We invite you to subscribe to our [slack workspace](http://rose-slack.netgroup.uniroma2.it:3000/) (channel #hpsr-tutorial)
for getting support about the rose-srv6 VM. See also our [contact page](https://netgroup.github.io/rose/rose-contacts.html).
 

### Option 1. Direct download of .ova image for Virtualbox

We assume that you have installed the latest version of [Virtualbox](https://www.virtualbox.org/wiki/Downloads) (6.1). 

Download [rose-srv6.ova](http://swift.cloud.garr.it/swift/v1/rose/vm/rose-srv6.ova) (3.3 GB).

Import *rose-srv6.ova* in Virtualbox (File-> Import Appliance)

### Option 2. Deploy using Vagrant

We assume that you have installed the latest version of [Virtualbox](https://www.virtualbox.org/wiki/Downloads) (6.1) and [Vagrant](https://www.vagrantup.com/downloads.html) (2.2.7).

#### Option 2.1 Deploy the VM from the Vagrant Cloud

```
vagrant init rosevm/xubuntu
vagrant up
```

#### 2.2 Download the .box file from our repository

Not available now! Stay tuned...

<!---
Download [rosevm-xubuntu.box](http://swift.cloud.garr.it/swift/v1/rose/vm/rosevm-xubuntu.box) (3.3 GB).

Create a new directory rose-vm in your PC and move the file *rosevm-xubuntu.box* inside. 

Create a text file called "Vagrantfile" in the rose-vm directory, with this content:
[Vagrantfile](https://github.com/netgroup/rose-vm/raw/master/vagrant-from-box-file/Vagrantfile), then run:

```
cd rose-vm
vagrant up
```
--->

## Advanced tips and tricks

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

<!---
### Scripted version of option 2.2 (for Linux)

```
git clone https://https://github.com/netgroup/rose-vm.git
cd rose-vm/vagrant-from-box-file
wget http://swift.cloud.garr.it/swift/v1/rose/vm/rosevm-xubuntu.box
vagrant up
```
--->

## Raw github version of this page (easier for working)

[https://github.com/netgroup/rose/blob/master/docs/rose-contacts.md](https://github.com/netgroup/rose/blob/master/docs/rose-contacts.md)
