Cloud Facts & Provisioning
==========================

[![Build Status](https://travis-ci.org/cocitizen/ansible-role-cloud.svg?branch=master)](https://travis-ci.org/coitizen/ansible-role-cloud)

Create and manage cloud infrastructure and resources easily, via a simple manifest. Currently supports common AWS components; more coming soon.


Background
----------

Ansible core includes powerful modules and inventory scripts that make working with cloud providers relatively easy. However, a number of these modules don't handle idempotency gracefully. That is, if one defines (for example) an EC2 instance task, and run Ansible, it will create a VM. If Ansible is run again, without modifying any playbooks, a second VM will be created.

This module seeks to improve on this by building a dynamic inventory, and mapping human-readable names to machine-readable resource IDs. By wrapping around Ansible's native cloud modules, we can work with a consistent, idempotent, cross-provider framework for managing cloud infrastructure. Better yet, it simplifies such usage by setting reasonable (configurable) defaults, and allowing the use of human-readable names across playbooks.


Role Variables
--------------

See [defaults/main.yml](defaults/main.yml) for a full breakdown of the available variables.


Dependencies
------------

None.


Example Playbook
----------------

Include in localhost as you would any other cloud role.

    - hosts: localhost
      roles:
        - cocitizen.cloud
      vars:
        cloud:
          amazon:
            vpcs:
              ...
            instances:
              ...


License
-------

GPLv3 or later.


Author Information
------------------

This role was created in 2017 by Christopher Gervais, CTO of [CoCitizen LLC](http://www.cocitizen.com/).
