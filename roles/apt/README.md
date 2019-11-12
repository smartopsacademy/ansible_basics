apt
=========

Configures the APT repositiries on a Debian/Ubuntu system.
Installs basic packages.
Upgrades installed packages.

Requirements
------------

Debian or Ubuntu.

Role Variables
--------------

apt_install_recommends: yes / no to enable/disable recommended packages install as well. Defaults to no.
apt_update_cache: yes / no to update apt cache before installing/upgrading. Defaults to 'yes'.
apt_force_apt_get: yes / no to use apt-get / aptitude for package management. Defaults to 'yes' (apt-get)
apt_upgrade: yes to upgrade your system automatically. Defaults to 'no' (do not upgrade)
apt_autoclean: yes to autoclean apt-get/aptitude cache (remove outdated downloaded deb files). Default to 'yes' (remove old deb files)
apt_autoremove: yes to automatically uninstall unneeded dependencies installed by removed packages. Defaults to 'no' (do not remove)

apt_base_packages: list of basic packages to install on your system. DO NOT USE IT for server installation! Use separate roles for that!
Defaults to:
  - 'lsb-release'
  - 'apt-transport-https'
  - 'ca-certificates'

apt_repositories: repositories to add. WARNING! Removes everything else. Add ALL your repos before using it!
Defaults to the default repos of Debian and Ubuntu based on your distribution and its version.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
         - apt

License
-------

CC-BA-SA

Author Information
------------------

See https://smartops.academy for more.
