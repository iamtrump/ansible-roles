acetv_docker
=========

Deploy AceTV inside docker

Role Variables
--------------

* `acetv_docker_port` — port for web app. Default is `80`.

Dependencies
------------

* docker

Example Playbook
----------------

- hosts: servers
  roles:
    - role: acetv_docker
      tags: acetv_docker
      vars:
        - acetv_docker_port: 8080
