dnsmasq
=======

Allow to install and configure dnsmasq using an additional hosts file


Role Variables
--------------


```
dnsmasq_listen_address
```
IP dnsmasq will listen on (this playbook always adds 127.0.0.1), if we don't define this variable we will use ansible_default_ipv4.address by default.

```
dnsmasq_addnhosts_file
```
Name of the file (stored as /etc/{{ dnsmasq_addnhosts_file }}.conf) containing hosts and IP definition (another file than /etc/hosts).

```
dnsmasq_local_domains
```
List of domains we want to manage with dnsmasq

```
dnsmasq_hosts:
  - host: myhost.example.com
    ip: 192.168.100.100
```
Dict containing the hosts/DNS names we manage with dnsmasq

Example Playbook
----------------

    - hosts: servers
      vars:
        dnsmasq_local_domains:
          - example.com
        dnsmasq_hosts:
          - hostname: demo.example.com
            ip: 192.168.100.100
      roles:
         - { role: dnsmasq }

License
-------

MIT

Author Information
------------------
Julian V. - AKA l00ptr 
