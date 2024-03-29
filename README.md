# vagrant-terraform

A vagrant project that builds Ubuntu 18.4 virtual box machine with Terraform.

## Prerequisites

* Install VirtualBox - [instructions](https://www.virtualbox.org/wiki/Downloads)
* Install Vagrant - [instructions](https://www.vagrantup.com/downloads.html)

## How to use this repository

* Set terraform version with environment variable `tf_ver` e.g. `tf_ver=0.11.14` or whatever version you want. 
* Build machine - `vagrant up`
* Destroy machine - `vagrant destroy`

In case the `tf_ver` env variable is not set the Vagrant project is set to default to the value set for the variable `tf_ver` in the Vagrantfile.

If the user has configured TF CLI `~/.terraformrc` and/or AWS credentials file `~/.aws/credentials` they will also be copied to the VM

## Examples

* Build a VM with specified TF version:

```Bash
tf_ver=0.11.14 vagrant up # build VM
vagrant ssh  # login to VM
cd /vagrant # on VM, go to the VM <-> HOST synced folder
```

* Change the TF version without rebuilding the VM

```Bash
tf_ver=0.12.2 vagrant provision # will re-run all provisioning
```

* Destroy VM

```Bash
vagrant destroy -f # does not prompt for confirmation
```
