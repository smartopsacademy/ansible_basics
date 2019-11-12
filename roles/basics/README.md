basics
=========

Configure some basics on your Debian/Ubuntu system.
- Replaces /etc/motd. Adds managed by Ansiblewarning.
- Configure the shell prompt (PS1) to be colorful.
- Removes cloud-init (we don't want to server manager systems, do we?)

Requirements
------------

None.

Role Variables
--------------

basics_colorprompt: Set true (default) for a color prompt, false to let the prompt as is.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
         - basics

License
-------

CC-BA-SA

Author Information
------------------

See https://smartops.academy for more.
