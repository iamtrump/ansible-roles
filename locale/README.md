locale
=========

The role sets locale and timezone

Role Variables
--------------

* `locale_name` — name and encoding of the locale. Default is `en_US.UTF-8`.
* `locale_timezone` — timezone. Default is `Europe/Moscow`.

Example Playbook
----------------

```
- hosts: servers
  roles:
    - role: locale
      tags: locale
```
