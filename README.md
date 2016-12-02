Ansible Role System Bootstrap
======================================

This role will boostraping instances, updates package tree and prepare system
for executing further roles. Also the hostname and host entries will be set.

Requirements
------------

- `ansible_distribution`: ["Gentoo", "CentOS"]

Role Variables
--------------

- `system_update`:
Perform update for system package tree. Possible values are yes or no. Default
yes.

- `system_hostname`:
System hostname. Default will be the variable `inventory_hostname`.

- `system_host_entries`:
Array with host entries. See [default vars file](defaults/main.yml)

Dependencies
------------

None.

Example Playbook
----------------
```
- hosts: all
  roles:
    - role: system-bootstrap
      system_update: yes
      system_hostname 'exaple.com'
      system_host_entries:
        - { ip: "127.0.0.1", name: "exaple.com", state: "present" }
        - { ip: "::1",       name: "exaple.com", state: "absent" }
```

License
-------

MIT

Author Information
------------------

- You can find more roles in my GitHub channel [vundb](https://github.com/vundb)
- Follow me on Twitter [@vundb](https://twitter.com/vundb)
