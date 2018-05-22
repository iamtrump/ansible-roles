openvpn
=========

Openvpn layer-3 internet gateway with certificate-based authentication.

Role Variables
--------------
### General
* `openvpn_server_name` — server name, default is `openvpn server`.
* `openvpn_clients` — list of clients. Specify value for `ip` to reserve static IP. `[{name: client, cn: client, ip: 192.168.88.5}]`.
* `openvpn_revoke` — list of names to revoke, default is `[]`.
* `openvpn_local_config_dir` — local dir to copy users’ configuration files. Default is `{{ inventory_hostname }}-openvpn-profiles`
### Network
* `openvpn_proto` — protocol to use (tcp/udp). Default is `udp`.
* `openvpn_port` — port, default is `161`.
* `openvpn_network` — openvpn network, default is `192.168.88.0/24`
### CA
* `openvpn_ca_root` — CA directory, default is `/etc/openvpn/pki`.
* `openvpn_ca_name` — CA common name, default is `CA`.
* `openvpn_ca_days` — number of days to certify CA certificate. Default: `3655`.
* `openvpn_c_days` — number of days to certify user cerificates. Default: `370`.
* `openvpn_c_country` — country, default: `RU`.
* `openvpn_c_province` — province, default: `Moscow`.
* `openvpn_c_city` — city, default: `Moscow`.
* `openvpn_c_organization` — organization. Default is `Corp`.
* `openvpn_c_ou` — organizational unit, default is `OU`.

Role Tags
---------

You can run role with following tags:
* `openvpn_add_clients` — to just add specified clients.
* `openvpn_revoke` — to just revoke specified certificates.
* `openvpn_clients` — to just list currently valid users.

Dependencies
------------

* ferm

Example Playbook
----------------

```
    - hosts: servers
      roles:
        - role: openvpn
          tags: openvpn
          vars:
            openvpn_server_name: Cool server
            openvpn_clients:
              - {name: mama, cn: My Mom}
              - {name: dad}
            proto: tcp
```
