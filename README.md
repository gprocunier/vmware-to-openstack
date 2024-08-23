# vmware-to-openstack
An ansible role that migrates VMWare Guests into OpenStack

## Usage
Modify the network_map.yml to link vmware network names to neutron network names
Modify the secrets.yml to provide vital data for interacting with vcenter and openstack (this should be an ansible vault!)
Modify the example migrate_vm.yml to suit your needs.


