LibreNMS autoprovision roles

To launch just type: "vagrant up librenms" or "vagrant up" - service will be
launched on 192.168.111.111 (configurable via Vagrantfile and inventory.ini)

Admin login|pass and snmp login|pass could be changed in librenms.yml
All settings are stored in role's defaults file.
vars/librenms/librenms.yml stores two lists made to substitute automatic
discovery of network devices upon service launch.

First list is for router devices:
librenms_devices:
  - 192.168.1.1

Second is for client devices:
librenms_client_devices:
  - 192.168.1.2
  - 192.168.1.3
  - ...

This solution automatically deploys and installs apache (by Larry Smith Jr) and
 memcached.
