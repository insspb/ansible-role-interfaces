Ansible Role: Interfaces
=========
- Master branch: [![Build Status](https://travis-ci.org/insspb/ansible-role-interfaces.svg?branch=master)](https://travis-ci.org/insspb/ansible-role-interfaces)
- Developer branch: [![Build Status](https://travis-ci.org/insspb/ansible-role-interfaces.svg?branch=develop)](https://travis-ci.org/insspb/ansible-role-interfaces)

Description
------------

This role will set local interfaces configuration on any host, input variable can be placed in inventory. Including routes.

Requirements
------------

No requiments yet.

Role Variables
--------------

```yaml
network_ether_interfaces:
    - device: "eth0"                    # DHCP interface example
      bootproto: "dhcp"
    - device: eth1                      # Static configuration example
      bootproto: static
      address: 10.99.0.10
      netmask: 255.255.255.0
      mtu: "1450"
      gateway: 10.99.0.1
      dns-servers: 8.8.8.8 8.8.4.4
      dns-search: myhost.com
      route:                            # Static routes for interface configuration
        - network: 192.168.0.0
          netmask: 255.255.255.0
          gateway: 10.99.0.11
```

Dependencies
------------

Independent role.

Example Playbook
----------------
```yaml
- hosts: all
  roles:
    - insspb.interfaces
```
Development information
----------------
This role is developed with community help. 

Process of development follows this rule: 

- You are free to add any pool request to develop branch. All request will be answered in timely manner. 
- If you want to made any contribution, but do not know where to start - check issues.
- Master branch updated just after significant changes in develop.
- Please include documentation for new features. 
- Please use variables.
- Please do not forget to set defaults.
- Please do your best to keep backward compatibility if possible.
- Please use packet installation as default software installation method. Source installation must be optional anywhere if possible.
- Please use official software developers repositories instead of general Debian/Ubuntu/Centos etc for main application. 
- Do you best to keep role independent from any other roles. User must have the way to choose what roles to use.

License
-------

MIT

Author Information
------------------

This role is contributed and maintained by [Andrey Shpak](http://www.ashpak.ru). I am always available for [hire](https://www.upwork.com/o/profiles/users/_~01a780866aa29e4429/).
