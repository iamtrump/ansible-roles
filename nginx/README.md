nginx
=========

The role installs nginx, php-fpm and acme.

Role Variables
--------------

* `nginx_www_root` — www root. Default is `/srv/www`.
* `nginx_tls_dir` — directory for TLS certificates. Default is `{{ nginx_www_root }}/tls`.
* `nginx_well_known_dir` — directory for acme challange. Default is `{{ nginx_www_root }}/well-known`.
* `nginx_acme_dir` — directory for acme.sh. Default is `{{ nginx_www_root }}/acme.sh`.
* `nginx_options` — parameters to set in nginx.conf. Default:
  ```
  - { name: user, value: www-data }
  - { name: server_names_hash_bucket_size, value: 64 }
  ```
* `nginx_options_additional` — additional parameters to set in nginx.conf. Default is empty.

Dependencies
------------

* ferm

Example Playbook
----------------

```
- hosts: servers
  roles:
    - role: nginx
      tags: nginx
      vars:
        - nginx_www_root: /opt/www
        - nginx_tls_dir: /var/certificates
```
