[![Build Status](https://travis-ci.com/oasis-roles/prepare_ocp_nodes.svg?branch=master)](https://travis-ci.com/oasis-roles/prepare_ocp_nodes)

prepare_ocp_nodes
===========

Basic description for prepare_ocp_nodes

Requirements
------------

Ansible 2.4 or higher

Red Hat Enterprise Linux 7 or equivalent

Valid Red Hat Subscriptions

Role Variables
--------------

Currently the following variables are supported:

### General

* `prepare_ocp_nodes_become` - Default: true. If this role needs administrator
  privileges, then use the Ansible become functionality (based off sudo).
* `prepare_ocp_nodes_become_user` - Default: root. If the role uses the become
  functionality for privilege escalation, then this is the name of the target
  user to change to.

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: prepare_ocp_nodes-servers
  roles:
    - role: oasis_roles.prepare_ocp_nodes
```

License
-------

GPLv3

Author Information
------------------

Author Name <authoremail@domain.net>