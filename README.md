# vmware-to-openstack
An ansible role that migrates VMWare Guests into OpenStack

## High Level Overview of the Role
![](https://github.com/gprocunier/vmware-to-openstack/blob/main/images/vmw2osp-hla.png?raw=true)

## Usage
Modify the `network_map.yml` to link vmware network names to neutron network names

Modify the `secrets.yml` to provide vital data for interacting with vcenter and openstack (this should be an ansible vault!)

Modify the example `migrate_vm.yml` to suit your needs.


## Requirements
An openstack VM (migration-factory) with access to the cinder/neutron/nova APIs

The following collections installed on the migration-factory

```
ansible collections:
  community.vmware  
  community.general
```

The virt-v2v/nbdkit tools on the migration-factory

VMWare VDDK installed on the migration factory:
  https://developer.broadcom.com/sdks/vmware-virtual-disk-development-kit-vddk/latest

You need an openstack `clouds.yaml` installed in the user on the migration-factory vm in openstack that the ansible playbook will operate as.

The ansible user on the migration-factory needs passwordless sudo to run virt-v2v.
