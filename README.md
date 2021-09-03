Ansible Role: amazon-ssm
========================

[![molecule](https://github.com/diodonfrost/ansible-role-amazon-ssm/workflows/molecule/badge.svg)](https://github.com/diodonfrost/ansible-role-amazon-ssm/actions)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-diodonfrost.amazon_ssm-660198.svg)](https://galaxy.ansible.com/diodonfrost/amazon_ssm)

This role provide a compliance for install amazon-ssm on your target host.

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):
```yaml
---
# defaults file for ansible-role-amazon-ssm

# Enable or disable sudo access for ssm-user on Linux instances
allow_sudo: true

# (Optional) Setup activation id, used with on-premise instances
activation_id:

# (Optional) Setup activation code, used with on-premise instances
activation_code:

# (Optional) Setup aws region, used with on-premise instances
aws_region:

# Configure SSM Agent to communicate through an https or/and https proxy
http_proxy_url:
https_proxy_url:
```

Dependencies
------------

None.

Example Playbook
----------------

This is a sample playbook file for deploying the Ansible Galaxy
role in a localhost and installing latest amazon-ssm version.

```yaml
---
- hosts: localhost
  become: true
  roles:
    - role: diodonfrost.amazon_ssm
```

Remove sudo access to the ssm-user account on Linux instances
```yaml
---
- hosts: localhost
  become: true
  roles:
    - role: diodonfrost.amazon_ssm
      vars:
        allow_sudo: false
```

Local Testing
-------------

This project uses [Molecule](http://molecule.readthedocs.io/) to aid in the
development and testing.

To develop or test you'll need to have installed the following:

* Linux (e.g. [Ubuntu](http://www.ubuntu.com/))
* [Docker](https://www.docker.com/)
* [Python](https://www.python.org/) (including python-pip)
* [Ansible](https://www.ansible.com/)
* [Molecule](http://molecule.readthedocs.io/)
* [Virtualbox](https://www.virtualbox.org/) (windows test only)
* [Vagrant](https://www.vagrantup.com/downloads.html) (windows test only)

### Testing with Docker ###

```shell
# Install requirements
pip install -r requirements-dev.txt

# Test role on CentOS 8
molecule test

# Test role on Ubuntu 20.04
image=ansible-ubuntu:20.04 molecule test

# Test role on Opensuse Leap
image=ansible-opensuse:leap molecule test
```

### Testing with Virtualbox ###

```shell
# Test role on Windows
molecule test -s windows

# Test role on Macos
molecule test -s macos
```

License
-------

Apache 2

Author Information
------------------

This role was created in 2019 by diodonfrost.
