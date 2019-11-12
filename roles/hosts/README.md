hosts
=========

Configures hostname, domain name and the hosts file.

Requirements
------------

Debian or Ubuntu.

Role Variables
--------------

hostname: Defaults to ansible_facts.hostname
domain_name: Defaults to ansible_facts.domain

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
         - hosts

License
-------

CC-BA-SA

Author Information
------------------

See https://smartops.academy for more.
