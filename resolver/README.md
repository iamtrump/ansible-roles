resolver
=========

The role configures nameservers in /etc/resolv.conf.

Role Variables
--------------

* `resolver_nameservers` — list of nameservers. Defailt is Google: `[8.8.8.8, 8.8.4.4]`.

Example Playbook
----------------

```
- hosts: servers
  roles:
    - role: resolver
      tags: resolver
```
