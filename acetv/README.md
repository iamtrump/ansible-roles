acetv
=========

The role configures acestream tv with web-interface. HLS only.

Role Variables
--------------

* acetv_fqdn — FQDN for web-interface. Default is {{ inventory_hostname }}.
* acetv_ssl — enable or disable https for web-interface. Default is false.
* acetv_user — user of acestream engine process Default is acetv.
* acetv_group — acestream user’s primary group. Default is acetv.
* acetv_port — acestream engine port. Default is 6878.
* acetv_prefix — directory in which acestream engine folder will be created. Default is /opt.
* acetv_channels_list — url of json with channels.
* acetv_frontend_dir — WWW root for web-interface. Default is {{ nginx_www_root }}/tv.
* acetv_password — password for web-interface. Default is acetv.

Dependencies
------------

* nginx

Example Playbook
----------------

```
- hosts: servers
  roles:
    - role: acetv
      tags: acetv
      vars:
        acetv_fqdn: www.mydomain.ru
        acetv_ssl: true
        acetv_password: my_super_password
```
