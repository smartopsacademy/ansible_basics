language_support
=========

Configures locales (Debian/Ubuntu) and language-support (Ubuntu)

Requirements
------------

Debian or Ubuntu.

Role Variables
--------------

languagesupport_installfull: Install full or basic language support on Ubuntu? Defaults to true (full)

languagesupport_locales: Configure the list of locales you want to install/enable on your system
Defaults to:
  - en_US.UTF-8

languagesupport_default: Configure the default locale. Don't forget to install it as well! Defaults to en_US.UTF-8

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
         - language_support

License
-------

CC-BA-SA

Author Information
------------------

See https://smartops.academy for more.
