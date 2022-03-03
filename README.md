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
     - geerlingguy.repo-epel
     - luisico.docker
     - role: ansible-nfs
       nfs_mode: client
     - role: trident
       trident_instances:
         - alias: netapp
           version: "19.10"
         - alias: edge
           version: latest
       trident_defaults:
         username: user
         password: password
         managementLIF: 10.10.10.1
         dataLIF: 10.10.10.20
         svm: nfs_svm
```

Any configuration options defined in `trident_instances` or `trident_defaults` will be transform into a JSON configuration file. For details about options, please, see [Trident's documentation](https://netapp-trident.readthedocs.io/en/latest/docker/install).

Licence
-------
Released under the [MIT license](https://opensource.org/licenses/MIT).

Author Information
------------------
Luis Gracia while at [The Rockefeller University](https://www.rockefeller.edu):
- lgracia [at] rockefeller.edu
- GitHub at [luisico](https://github.com/luisico)
- Galaxy at [luisico](https://galaxy.ansible.com/luisico)

Vineet Palan while at [The Rockefeller University](https://www.rockefeller.edu):
- GitHub at [vineetpalan](https://github.com/vineetpalan)
