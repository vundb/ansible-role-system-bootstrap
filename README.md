Ansible Role System Bootstrap
======================================

This role will boostraping instances, updates package tree and prepare system
for executing further roles.

The hostname and host entries will be set.

The Timezone will be configured.


Supported Distributions
-----------------------

- Gentoo

Role Variables
--------------

- `system_update`:
Perform update for system package tree. Possible values are yes or no. Default
yes.

- `system_profile`:
Gentoo's system profile to use. Default value is `default/linux/amd64/17.0`.

- `system_hostname`:
System hostname. Default will be the variable `inventory_hostname`.

- `system_timezone`:
System timezone in the timezone database format.

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
    - role: vundb-system-bootstrap
      system_update: yes
      system_hostname 'exaple.com'
      system_timezone: 'Europe/Berlin'
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
