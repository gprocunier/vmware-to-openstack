# vmware-to-openstack
An ansible role that migrates VMWare Guests into OpenStack.  This role can be positioned with Ansible Automation Platform to enable on-demand Migration-as-a-Services.

## High Level Overview of the Role
![](https://github.com/gprocunier/vmware-to-openstack/blob/main/images/vmw2osp-hla.png?raw=true)

## Usage
Modify the `network_map.yml` to link vmware network names to neutron network names

Modify the `secrets.yml` to provide vital data for interacting with vcenter and openstack (this should be an ansible vault!)

Modify the example `migrate_vm.yml` to suit your needs.


## Requirements
1. An openstack VM (migration-factory) with access to the vcenter/esxi hosts as well as cinder/neutron/nova APIs
( For example a RHEL 9 instance deployed with the required components listed below.  In the Migration-as-a-Service scenario, the prepared VM would be written out as a glance image and stood up on-demand as part of the AAP workflow. )

2. The following collections installed on the migration-factory

```
ansible collections:
  community.vmware  
  community.general
```

3. The virt-v2v/nbdkit tools on the migration-factory

4. VMWare VDDK installed on the migration factory:
  https://developer.broadcom.com/sdks/vmware-virtual-disk-development-kit-vddk/latest

5. You need an openstack `clouds.yaml` installed in the user on the migration-factory vm in openstack that the ansible playbook will operate as.

6. The ansible user on the migration-factory needs passwordless sudo to run virt-v2v.
