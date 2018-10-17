Ansible RedHat ISO Image Role
==================

This role creates an automated RedHat ISO Image on your localhost.

Requirements
------------

This role was developed using Ansible **2.6**. Backwards compatibility is not guaranteed.

**Supported platforms:**

```yaml
CentOS:
  versions:
    - 6
    - 7
RHEL:
  versions:
    - 6
    - 7
```

Role Variables
--------------

This role has multiple variables. The defaults for all these variables are the following:

```yaml
---
# https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/anaconda_customization_guide/sect-boot-menu-customization

image_src_dir: "../.images/{{ image_file_name }}"
image_dest_dir: "../.images/{{ image_file_name }}"

image_name: 'CentOS 7 x86_64'
image_file_name: 'CentOS-7-x86_64-Minimal-1804'
image_dl_url: 'http://ftp.tu-chemnitz.de/pub/linux/centos/7.5.1804/isos/x86_64/CentOS-7-x86_64-Minimal-1804.iso'
image_dl_checksum: 'sha256:714acc0aefb32b7d51b515e25546835e55a90da9fb00417fbee2d03a62801efd'
image_bios_conf_file: 'isolinux/isolinux.cfg'
image_uefi_conf_file: 'EFI/BOOT/grub.cfg'
image_boot_name: "{{ image_name|replace(' ','\\x20') }}"

# Pick first disks with minimal physical size image_disk_drive_min_size (GiB)
# until a overall minimal logical OS volume size image_disk_volume_min_size (GiB)
# and create a logical OS volume with maximal size image_disk_volume_max_size (GiB)
image_disk_drive_min_size: 10
image_disk_volume_min_size: 60
image_disk_volume_max_size: 120

image_hosts: []
image_root_password: 'centos'
image_country_code: 'de'
image_timezone: 'Europe/Berlin'
image_network_bootproto: 'dhcp'
image_network_device: 'eth0'
image_network_static_netmask: '255.255.255.0'
image_network_static_gateway: '192.168.1.1'
image_network_static_nameserver: ['192.168.1.1']
# If image_network_bootproto is 'static' use image_network_static_hosts to create custom static host ISO images
#image_network_static_hosts:
#  - { ip: '192.168.1.1', hostname: 'host01'}
image_network_static_hosts: []
```

Dependencies
------------

None

Example Playbook
----------------

This is a sample playbook file for the Ansible role to create an automated CentOS ISO image on a localhost; made for network releases via DHCP.

```yaml
---
- hosts: localhost
  become: yes
  roles:
    - role: redhat-iso-image
```

This is a sample playbook file for the Ansible role to create automated CentOS ISO images on a localhost with custom variables; made for static network configuration.

```yaml
---
- hosts: localhost
  become: yes
  roles:
    - role: redhat-iso-image
      vars:
        image_network_bootproto: 'static'
        image_network_static_netmask: '255.255.252.0'
        image_network_static_gateway: '10.0.0.1'
        image_network_static_nameserver:
          - '10.0.2.1'
          - '10.0.3.1'
        image_network_static_hosts:
          - { ip: '10.0.1.100', name: 'host01'}
          - { ip: '10.0.1.200', name: 'host02'}
```

To run any of the above sample playbooks create a `image-onprem.yml` file and paste the contents. Executing the Ansible Playbook is then as simple as executing `ansible-playbook image-onprem.yml`.

License
-------

[Apache License, Version 2.0](https://github.com/rembik/ansible-role-redhat-iso-image/blob/master/LICENSE)

Author Information
------------------

Rembik Rain
