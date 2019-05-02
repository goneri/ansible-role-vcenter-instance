Role Name
=========

Deploy a VCenter from the ISO on a ESXi host.

Requirements
------------

- an ESXI (tested with 6.5 or 6.7)
- the ISO of Vcenter (tested with VMware-VCSA-all-6.7.0-11726888.iso) 
- a Linux system

Role Variables
--------------

Variables are documented in the `defauls/main.yaml`.

Dependencies
------------

none

Example Playbook
----------------

```yaml
- hosts: localhost
  roles:
  - role: vsphere-lab
  - role: vcenter-instance
    vars:
      vcenter_instance_deploy_from: 'datastore'
      vcenter_instance_network_name: VM Network
      vcenter_instance_datastore_name: esx_lab
      vcenter_instance:
        network:
          address: 192.168.123.90
          prefix: 24
          gateway: 192.168.123.1
          dns: ['192.168.123.1']
        esxi:
          hostname: esxi-vcenter
          username: root
          password: root
      vcenter_instance_name: vCenter-Server-Appliance
      vcenter_instance_password: vCenter-Server-Appliance
      vcenter_instance_VCSA_iso: /home/goneri/Downloads/VMware-VCSA-all-6.7.0-11726888.iso
```

License
-------

BSD

Author Information
------------------

Gonéri Le Bouder
