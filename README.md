infra_server_lifecycle_foreman
=========

A simple role to install foreman with support of moving the /var/lib/pulp directory to a Logical Volume

Requirements
------------

NA

Releases
------------

|Branch|Status|Description| Date
|---	|---	|---	|---
|main|Unstable|Development Branch|Now
|1.0.0|Release|Release 1.0.0|04-09-2021


Role Variables
--------------

**top level vars**
|Variable|Level|Type|Description
|---|---|---|---	
|foreman_initial_org|Default|string|Foreman Initial Organization
|foreman_initial_location|Default|string|Foreman Initial Location
|foreman_initial_admin_username|Vars|string|Foreman Admin Usernamae
|foreman_initial_admin_password|Default|string|Foreman Admin Password
|move_pulp_dir_in_an_lvm|Default|string|Whether /var/lib/pulp needs to be moved to a logical volume
|pulp_lvm|Default|string|The Logical Volume to move the pulp directory



Dependencies
------------
NA


Example Playbook
----------------


```
---
- hosts: foreman
  become: yes
  roles:
    - role: infra_server_lifecycle_foreman
      vars:
        foreman_initial_org: LabOrg
        foreman_initial_location: London
        foreman_initial_admin_username: admin
        foreman_initial_admin_password: welcome1
        move_pulp_dir_in_separate_partition: yes
        pulp_lvm: /dev/vg_pulp/lv_pulp
```

License
-------

Apache-2.0

Author Information
------------------

```
Petros Petrou
email: ppetrou@gmail.com
web: www.petrospetrou.co.uk
```
