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
* EPEL repositories need to be available, ie using role `geerlingguy.repo-epel`.  
* Docker engine needs to installed, ie using role `luisico.docker`.   
* NFS Utils needs to be installed if NFS-based storage is used. ie using `luisco.nfs`   
* iSCSI packages needs to be installed if iSCSI-based storage is used.   
  For more details visit https://netapp-trident.readthedocs.io/en/stable-v19.07/docker/install/host_config.html#iscsi

Example Playbook
----------------
Example:
```
- hosts: all
  roles: 
     - role: geerlingguy.repo-epel
     - role: luisico.docker
     - role: ansible-nfs
       vars:
         nfs_mode: client
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
