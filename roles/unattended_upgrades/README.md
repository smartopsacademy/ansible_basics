unattended_upgrades
=========

Installs and configures unattended upgrades to keep your server up to date.

Requirements
------------

Debian or Ubuntu.

Role Variables
--------------

unattended_upgrades_enabled: True / False to enable / disable unattended upgrades globally. Defaults to true.
unattended_upgrades_generic: True / False to anable all upgrades (generic upgrades). Defaults to false (install only security upgrades)

unattended_upgrades_packages: packages to install
Defaults to:
  - 'unattended-upgrades'

unattended_upgrades_security_origins: list of security repos. Defaults based on your distro / version.

unattended_upgrades_generic_origins: list of generic origins. Defaults based on your distro / version.

unattended_upgrades_autofixinterrupteddpkg: True / False. Use "dpkg --configure -a" to fix interrupted installs. Defaults to true (fix).
unattended_upgrades_minimalsteps: True / false. Install packages one by one (true) or in one shot (false). Defaults to true.
unattended_upgrades_mailfrom: Default: system_mailfrom
unattended_upgrades_mailto: Default: system_mailto
unattended_upgrades_mailonlyonerror: True / False. Send email only on error (true) ar always (false). Defaults to true.
unattended_upgrades_removeunusedkernel: True / False. Remove old kernel versions not in use? Defaults to true (remove).
unattended_upgrades_removeunused: True / False. Remove unused dependencies? Default to false (do not remove).
unattended_upgrades_autoreboot: True / False. Automatically reboot server after a kernel upgrade? Defaults to false (do not reboot).
unattended_upgrades_autoreboottime: If we auto reboot, when? 2:30 AM if not running virtualised, 2:42 otherwise.

Dependencies
------------

None. Do not forget to configure the apt repositories!

Example Playbook
----------------

    - hosts: servers
      roles:
         - unattended_upgrades

License
-------

CC-BA-SA

Author Information
------------------

See https://smartops.academy for more.
