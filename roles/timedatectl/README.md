timedatectl
=========

Configures systemd timedatectl (timezone, NTP).

Requirements
------------

Debian or Ubuntu.

Role Variables
--------------

timesyncd_enabled: true / false to enable / disable timesyncd management.
Defaults to false in LXC containers, ture in all other cases.

timedatectl_servers: list of time servers to use
Defaults to:
  - "0.debian.pool.ntp.org"
  - "1.debian.pool.ntp.org"

timedatectl_servers_fallback: list of fallback time servers
Defaults to:
  - "2.debian.pool.ntp.org"
  - "3.debian.pool.ntp.org"

timedatectl_timezone: Timezone to use. Default: "Etc/UTC"

Dependencies
------------

None.

Example Playbook
----------------

    - hosts:
        servers:
          timedatectl_timezone: "Europe/London"
      roles:
         - timedatectl

License
-------

CC-BA-SA

Author Information
------------------

See https://smartops.academy for more.
