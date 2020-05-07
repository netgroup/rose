# ROSE ready-to-go Virtual Machine

A ready-to-go Virtual Machine is available, to be used for tutorial and/or development purposes.

The ROSE VM includes an integrated development and test environment, based on Mininet and the
Linux kernel for the SRv6 data plane.

## How to install

The ROSE VM is currently available for the Virtualbox hypervisor ([download](https://www.virtualbox.org/wiki/Downloads)).
We also support Vagrant ([download](https://www.vagrantup.com/downloads.html)) to manage the provisioning of the VM.
 

### Option 1. Direct download of .ova image for Virtualbox

We assume that you have installed the latest version of [Virtualbox](https://www.virtualbox.org/wiki/Downloads). 

Download [rose.v2.0.ova](http://swift.cloud.garr.it/swift/v1/rose/vm/rose-srv6.ova).

Import the .ova in Virtualbox (File-> Import Appliance)

### Option 2. Deploy using Vagrant

We assume that you have installed the latest version of [Virtualbox](https://www.virtualbox.org/wiki/Downloads) and [Vagrant](https://www.vagrantup.com/downloads.html).

#### 2.1 Deploy the VM from the Vagrant Cloud

Simply run

```
vagrant init rosevm/xubuntu
vagrant up
```
If you want to change the VM name to rose-srv6, edit the Vagrantfile generated after the first command by adding:

```
  config.vm.provider "virtualbox" do |v|
    v.name = "rose-srv6"
  end
```

#### 2.2 Download the .box file from our repository

Clone the repository:
```
git clone https://https://github.com/netgroup/rose-vm.git
cd rose-vm
```

Download [rosevm-xubuntu.box](http://swift.cloud.garr.it/swift/v1/rose/vm/rosevm-xubuntu.box) and copy it
in the directory [vagrant-from-box-file](vagrant-from-box-file)

The Vagrantfile is [vagrant-from-box-file/Vagrantfile](vagrant-from-box-file/Vagrantfile).

```
cd vagrant-from-box-file
vagrant up
```


