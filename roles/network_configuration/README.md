network_configuration
=========

Configures network interfaces on Debian and Ubuntu.
On Debian, it uses the legacy ifupdown (/etc/network/interfaces.d/) method.
On Ubuntu, it uses netplan.
Both can be changed using variables.

Requirements
------------

Debian or Ubuntu.

Role Variables
--------------

netplan_supported: List of distribution supporting the netplan.io method. Defaults to: ["Ubuntu"]
network_configuration_mode: netplan / ifupdown. Defaults to netplan if it's supported, ifupdown otherwise.

common_packages: packages to install (netplan.io or ifupdown installed separately!)
Defaults to:
  - bridge-utils (you need it only if you want to manage bridges with ifupdown or manually manage them with netplan)

netplan_packages: packages to install when using the netplan method
Defaults to:
  - netplan.io

netplan_remove_existing: true / false to remove / leave alone the existing netplan yamls. Defaults to: true (remove and replace everything)
netplan_config: Netplan yaml file name to generate. Defaults to /etc/netplan/ansible.yaml
netplan_renderer: Netplan renderer to use. See netplan documentation for more! Defaults to networkd
netplan_configuration: Network configuration. Defaults to none ([]). See examples for more!

ifupdown_packages: packages to install when using the ifupdown method
Defaults to:
  - ifupdown

ifupdown_remove_existing: true / false to remove / leave alone the existing files in interfaces.d. Defaults to: true (remove and replace everything)
ifupdown_config: Network config file to generate. Default: /etc/network/interfaces.d/ansible
ifupdown_interfaces: Network configuration. Defaults to none ([]). See examples for more!

resolved_config: DNS config for systemd-resolved. Defaults to none ([]). See examples for more!

Dependencies
------------

None.

Example Playbook
----------------

    - hosts:
        server-netplan:
          netplan_configuration:
            network:
              version: 2
              renderer: networkd
              ethernets:
                eth0:
                  dhcp4: yes
                  dhcp6: no
                  optional: yes
        server-ifupdown:
          ifupdown_interfaces:
            lan:
              device: eth0
              mode: static
              auto: "true"
              config:
                address: "10.11.12.13"
                netmask: "24"
                gateway: "10.11.12.1"
          resolved_config:
            dns:
              - 127.0.0.1
              - 10.11.12.1
            domains:
              - smartopsacademy.lan
      roles:
         - network_configuration

License
-------

CC-BA-SA

Author Information
------------------

See https://smartops.academy for more.
