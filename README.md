# vmware-to-openstack
An ansible role that migrates VMWare Guests into OpenStack

## Usage
Modify the `network_map.yml` to link vmware network names to neutron network names

Modify the `secrets.yml` to provide vital data for interacting with vcenter and openstack (this should be an ansible vault!)

Modify the example `migrate_vm.yml` to suit your needs.


## Requirements
```
ansible collections:
  community.vmware  
  community.general
```

The virt-v2v/nbdkit tools.

VMWare VDDK:
  https://developer.broadcom.com/sdks/vmware-virtual-disk-development-kit-vddk/latest

You need an openstack `clouds.yaml` installed in the user on the conversion appliance vm in openstack that the ansible playbook will operate as.

The ansible user on the conversion appliance needs passwordless sudo to run virt-v2v.
