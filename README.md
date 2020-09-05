Debian-Users
============

Manage local users

Requirements
------------

This role requires a debian compliant system such as ubuntu.

Role Variables
--------------

debian.users:
  - name: user1
    shell: /bin/bash
  - name: user2
    shell: /usr/bin/zsh
    keys:
      - user2_rsa.pub
    groups:
      - sudo
      - www-data
  - name: user3
    remove: yes

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: cowops.debian-users }

Tasks
-----

  - Install sudo command, bash and zsh shell
  - Add system users
  - Import system users' keys
  - Remove deprecated users
  - Add wheel group
  - Enable passwordless sudo for wheel group
  - Add sudo users to wheel group

License
-------

BSD
