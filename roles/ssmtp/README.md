ssmtp
=========

Installs and configures a nullmailer (ssmtp).

Requirements
------------

Debian or Ubuntu.

Role Variables
--------------

ssmtp_packages: packages to install
Defaults:
  - ssmtp
  - bsd-mailx

ssmtp_mailname: Name of the server (NOT the From in the email!), defaults to ansible_fqdn
ssmtp_mailhub: Relay server name, defaults to smtp.eu.mailgun.org
ssmtp_fromoverride: true / false to allow / deny From name override. Defaults to false (From cannot be overriden by a program)
ssmtp_hostname: Server's FQDN. Defaults to ansible_fqdn
ssmtp_port: Relay server port. Defaults to submission (587).
ssmtp_rewritedomain: From domain (@domain.tld). Use valid senders! Defaults to ansible_domain
ssmtp_root: Who gets email addressed to userids < 1000 (e.g. root)? E-mail address. Defaults to system_mailto
ssmtp_tls: true / false to use / don't use SSL/TLS when connecting to the relay server. Defaults to false (it's NOT for STARTTLS!)
ssmtp_starttls: true / false to use don't use STARTTLS when connectiong to the relay server. Defaults to true (use STARTTLS)

Dependencies
------------

None.

Example Playbook
----------------

    - hosts:
        servers:
          ssmtp_mailhub: "smtp.eu.mailgun.org"
          ssmtp_port: 587
          ssmtp_rewritedomain: "smartops.academy"
      roles:
         - ssmtp

License
-------

CC-BA-SA

Author Information
------------------

See https://smartops.academy for more.
