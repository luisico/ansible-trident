# trident
                            
Install and configure trident (netap storage orchestrator)

Requirements
------------
See `meta/main.yml`.

Role Variables
--------------
See `defaults/main.yml` for all options.

Dependencies
------------
EPEL repositories need to be available, ie using role `geerlingguy.repo-epel`.

Docker engine needs to installed, ie using role `luisico.docker`.

Example Playbook
----------------
Example:
```
- hosts: all
  roles: 
     - role: trident
       vars:
         trident_cluster_user: admin
         trident_cluster_password: password
         trident_cluster_management_ip: 10.10.10.1
         trident_svm_ip: 10.10.10.20
         trident_svm_name: nfs_svm
         trident_nfs_server: True
  
```

Licence
-------
Released under the [MIT license](https://opensource.org/licenses/MIT).

Author Information
------------------
Vineet Palan while at [The Rockefeller University](https://www.rockefeller.edu):
- vpalan [at] rockefeller.edu
- GitHub at [vineetpalan](https://github.com/vineetpalan)
- Galaxy at [vineetpalan](https://galaxy.ansible.com/vineetpalan)
