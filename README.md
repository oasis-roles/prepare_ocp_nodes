[![Build Status](https://travis-ci.com/oasis-roles/prepare_ocp_nodes.svg?branch=master)](https://travis-ci.com/oasis-roles/prepare_ocp_nodes)

prepare\_ocp\_nodes
===========

Installs basic tools required on all OpenShift Compute Platform (OCP) nodes
before the OpenShift installer can be executed against them.

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
* `prepare_ocp_nodes_hostname` - Default: `hostvars['ansible_hostname']`. Use this
 to set the hostname of the machine if it differs from the detected one. If thre
 is an unuseful default hostname already, you can use the [hostname](https://github.com/oasis-roles/hostname)
 role to set that up.

Dependencies
------------

The system needs to be able to auto-discover its IPv4 address. If you are running
in an environment where this can't be auto-discovered, you need to figure out how
to populate the `ansible_default_ipv4.address` field before running, as this role
will query that value. For example, in a CentOS container image, Ansible cannot
auto-discover the IP address, so `ansible_default_ipv4` will not be populated.

Example Playbook
----------------

```yaml
- hosts: prepare_ocp_nodes-servers
  roles:
    - role: oasis_roles.prepare_ocp_nodes
  vars:
    prepare_ocp_nodes_hostname: "{{ inventory_hostname }}"
```

License
-------

GPLv3

Author Information
------------------

Greg Hellings <greg.hellings@gmail.com>
