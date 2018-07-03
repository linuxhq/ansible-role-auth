# ansible-role-auth

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-auth.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-auth)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-auth-blue.svg?style=flat)](https://galaxy.ansible.com/linuxhq/auth)
[![License](https://img.shields.io/badge/license-GPLv3-brightgreen.svg?style=flat)](https://github.com/linuxhq/ansible-role-auth/blob/master/COPYING)

Linux - Manage users, groups, and public ssh keys

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    auth_groups: {}
    auth_users: {}
      
## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.auth
          auth_groups:
            wheel:
              gid: 10
              system: true
          auth_users:
            root:
              shell: /sbin/nologin
              uid: 0
            tkimball:
              exclusive: yes
              gid: 10
              key: ssh-rsa {...}
              key_options: []
              password: {...}
              uid: 1000

## License

Copyright (C) 2018 Taylor Kimball <tkimball@linuxhq.org>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>.
