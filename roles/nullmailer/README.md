ssmtp
=========

Installs and configures a nullmailer (ssmtp or msmtp).

Requirements
------------

Debian or Ubuntu.

Role Variables
--------------

nullmailer: select the desired nullmailer. Supported options are ssmtp and mstmp. Defaults to ssmtp on Ubuntu and msmtp on Debian.

nullmailer_mailname: Name of the server (the From in the email). Defaults to ansible_facts.domain
nullmailer_fqdn: Name for the HELO/EHLO command. Defaults to ansible_facts.fqdn
nullmailer_fromoverride: true / false to allow / deny From name override. Defaults to false (From cannot be overriden by a program)
nullmailer_from: the default sender address. Defaults to root@nullmailer_mailname
nullmailer_to: Who gets the email? E-mail address. Defaults to system_mailto

nullmailer_host: Relay server name, defaults to smtp.eu.mailgun.org
nullmailer_port: Relay server port. Defaults to submission (587).
nullmailer_tls: true / false to use / don't use SSL/TLS when connecting to the relay server. Defaults to false (it's NOT for STARTTLS!)
nullmailer_starttls: true / false to use don't use STARTTLS when connectiong to the relay server. Defaults to true (use STARTTLS)

Dependencies
------------

None.

Example Playbook
----------------

    - hosts:
        servers:
          nullmailer_host: "smtp.eu.mailgun.org"
          nullmailer_port: 587
          nullmailer_mailname: "smartops.academy"
          nullmailer_to: "admin@{{ nullmailer_mailname }}"
      roles:
         - nullmailer

License
-------

CC-BA-SA

Author Information
------------------

See https://smartops.academy for more.
