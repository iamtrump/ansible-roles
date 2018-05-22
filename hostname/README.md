hostname
=========

The role configureis hostname and /etc/hosts.

Role Variables
--------------

* `hostname` — hostname to set. Default is `{{ inventory_hostname }}`.
Example Playbook
----------------

```
- hosts: servers
  roles:
    - role: hostname
      tags: hostname
      vars:
        hostname: coolhost
```
