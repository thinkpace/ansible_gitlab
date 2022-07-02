thinkpace.ansible_gitlab
========================

This is a very simple role to install GitLab on Docker.

Requirements
------------

Docker needs to be installed on the system, [thinkpace.ansible_docker](https://galaxy.ansible.com/thinkpace/ansible_docker) can be used to achieve this. Furthermore, a specific user needs to exist which is the owner of GitLab files on host system, you can use [thinkpace.ansible_user](https://galaxy.ansible.com/thinkpace/ansible_user) to do this. Make sure configured ports are not in use.

Role Variables
--------------

Role is using several variables which must be defined in following structure:

```
gitlab:
  hostname: "gitlab"
  url_with_protocol: "http://gitlab.example.com"
  ports:
    http: 80
    https: 443
    ssh: 22
  user: "gitlab"
  working_dir: "/gitlab"
  backup:
    dir: "/backup/gitlab"
    hour: 0
    minute: 0
```

See also [vars_sample.yml](vars_sample.yml).

Dependencies
------------

This role is tested on Ubuntu 20.04 (Focal Fossa).

Example Playbook
----------------

Make sure to install this role is installed before using:

`ansible-galaxy install thinkpace.ansible_gitlab`

You can update this role with the --force flag:

`ansible-galaxy install --force thinkpace.ansible_gitlab`

This role can be used like following:

```
    - hosts: servers
      roles:
        - { role: thinkpace.ansible_gitlab }
```

License
-------

GNU Affero General Public License v3.0

Author Information
------------------

[Tobias Baus](https://tobiasbaus.de)
