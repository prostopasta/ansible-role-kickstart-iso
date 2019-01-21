Ansible Role: Kickstart ISO
===========================

[![Build Status](https://img.shields.io/travis/rembik/ansible-role-kickstart-iso/master.svg?logo=travis&logoColor=EEE)](https://travis-ci.org/rembik/ansible-role-kickstart-iso)
[![GitHub release](https://img.shields.io/github/release/rembik/ansible-role-kickstart-iso.svg?&logo=github&logoColor=EEE)](https://github.com/rembik/ansible-role-kickstart-iso/releases)
[![Ansible Role](https://img.shields.io/ansible/role/36241.svg?logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABoAAAAaCAYAAACpSkzOAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAKeSURBVEhLrZb9ddowFMWNYQA+/ycTlEwQMkHpBGGEMgFhgsAEdSYomaBkAtgg/p/PAfjo7wrZtYstOz2953AkPT3p+j3dJ1HxCrDf73un06lfqVS+Mqzz65oJzwuxhefz+b1arQaNRuNg7ZnIJVqv133f98ds1remIgT4TiAM7TiFGyIiqF8ulzG/IQsVwafAukmr1Xq2wxgpIkvyg+7gavlnzJvN5jfbN4iJ/iNJhBSZb1uFPKYpQxIggJHtuzDYbDZD279GpINHOb+MxQE+5oBA7qSw3W73E5Pzw6z/vQRiIpK6zEwBEEcsYyT/aowOSEw2U15FdcJgaWYKwOaPtVotPB6PvU6nM99utx9sFtVVJqIs+CpGayvCnM0XnM+QhS/WVioqOAas8R+szYlEqp4UBZnosnZqbU7g98UntJ4d5wKfkJQtEM0gSpVyb88r0LgA3VjeBXjVpjof5VwGWqM4iGdqXcDXEDmvGW1M6IFSBdmK/h22lXKvOpGNceb9loSInE5suGAz3dJDVGbUyV12TzNlzkgXoolaBw4+zk4iRBClRiLoQfihkuB6GUEwU6QU+1yRW78bsG7ls/DNjm+gFEnSSRHQqgiXpO17u92eKlqdH/ZcUfCx776+xo6zYD4CnyczSoCzeuEaiupJH5CZPkUqxZq7LuvekoMOnm6dqJeK5DqThqLG71FRcYb7v/2YN++TISLPSsfezCSAbUFTZ3GZWpMSU37Y4kvY1JE6NDdVzkL9VygkEbL8IBrZvdMvbJmr/xOYSpm2/+fhE+yL6BJHWajGUuJIRRSBQ33GsdQblYTOROlC9jdSzyQSVIgsEln8HOdBBDQzDl51lVm4uURJqGCppQc2jA5cStSNElKMb9TJKo/gCs/7DZRaZqjl0/EmAAAAAElFTkSuQmCC)](https://galaxy.ansible.com/rembik/kickstart_iso)
[![Ansible Role downloads](https://img.shields.io/ansible/role/d/36241.svg?logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABoAAAAaCAYAAACpSkzOAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAKeSURBVEhLrZb9ddowFMWNYQA+/ycTlEwQMkHpBGGEMgFhgsAEdSYomaBkAtgg/p/PAfjo7wrZtYstOz2953AkPT3p+j3dJ1HxCrDf73un06lfqVS+Mqzz65oJzwuxhefz+b1arQaNRuNg7ZnIJVqv133f98ds1remIgT4TiAM7TiFGyIiqF8ulzG/IQsVwafAukmr1Xq2wxgpIkvyg+7gavlnzJvN5jfbN4iJ/iNJhBSZb1uFPKYpQxIggJHtuzDYbDZD279GpINHOb+MxQE+5oBA7qSw3W73E5Pzw6z/vQRiIpK6zEwBEEcsYyT/aowOSEw2U15FdcJgaWYKwOaPtVotPB6PvU6nM99utx9sFtVVJqIs+CpGayvCnM0XnM+QhS/WVioqOAas8R+szYlEqp4UBZnosnZqbU7g98UntJ4d5wKfkJQtEM0gSpVyb88r0LgA3VjeBXjVpjof5VwGWqM4iGdqXcDXEDmvGW1M6IFSBdmK/h22lXKvOpGNceb9loSInE5suGAz3dJDVGbUyV12TzNlzkgXoolaBw4+zk4iRBClRiLoQfihkuB6GUEwU6QU+1yRW78bsG7ls/DNjm+gFEnSSRHQqgiXpO17u92eKlqdH/ZcUfCx776+xo6zYD4CnyczSoCzeuEaiupJH5CZPkUqxZq7LuvekoMOnm6dqJeK5DqThqLG71FRcYb7v/2YN++TISLPSsfezCSAbUFTZ3GZWpMSU37Y4kvY1JE6NDdVzkL9VygkEbL8IBrZvdMvbJmr/xOYSpm2/+fhE+yL6BJHWajGUuJIRRSBQ33GsdQblYTOROlC9jdSzyQSVIgsEln8HOdBBDQzDl51lVm4uURJqGCppQc2jA5cStSNElKMb9TJKo/gCs/7DZRaZqjl0/EmAAAAAElFTkSuQmCC)](https://galaxy.ansible.com/rembik/kickstart_iso)

This role creates custom kickstart ISO images for:
* RHEL 7
* CentOS 7

Requirements
------------

None.

Role Variables
--------------

This role has multiple variables. The defaults for all these variables are the following:

```yaml
---
# https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/anaconda_customization_guide/sect-boot-menu-customization

image_name: 'CentOS 7 x86_64'
image_type: 'Minimal'
image_check_url: 'http://mirror.centos.org/centos/7/isos/x86_64/sha256sum.txt.asc'
image_base_url: 'http://isoredirect.centos.org/centos/7/isos/x86_64/'

image_src_dir: ".images/{{ image_name|replace(' ','-') }}"
image_dest_dir: ".images/{{ image_name|replace(' ','-') }}"

image_bios_conf_file: 'isolinux/isolinux.cfg'
image_uefi_conf_file: 'EFI/BOOT/grub.cfg'
image_boot_name: "{{ image_name|replace(' ','\\x20') }}"

# Pick first disks with minimal physical size image_disk_drive_min_size (GiB)
# until a overall minimal logical OS volume size image_disk_volume_min_size (GiB)
# and create a logical OS volume with maximal size image_disk_volume_max_size (GiB)
image_disk_drive_min_size: 10
image_disk_volume_min_size: 60
image_disk_volume_max_size: 120

image_root_password: 'centos'
image_language: 'de'
image_country: 'DE'
image_timezone: 'Europe/Berlin'
image_network_bootproto: 'dhcp'
image_network_device: 'eth0'
image_network_static_netmask: '255.255.255.0'
image_network_static_gateway: '192.168.1.1'
image_network_static_nameserver: ['192.168.1.1']
# If image_network_bootproto is static use image_network_static_hosts
# to create custom static host ISO images
# image_network_static_hosts:
#   - {ip: '192.168.1.1', name: 'host01'}
```

Dependencies
------------

None.

Example Playbook
----------------

This is a sample playbook file for the Ansible role to create an kickstart CentOS 7 ISO image on
localhost; made for network releases via DHCP.

```yaml
---
- hosts: localhost
  become: true

  roles:
    - role: rembik.kickstart_iso
```

This is a sample playbook file for the Ansible role to create kickstart CentOS 7 ISO images on
localhost with custom variables; made for static network configuration.

```yaml
---
- hosts: localhost
  become: true

  pre_tasks:
    - name: Get all hosts (including IP) from inventory
      set_fact:
        image_network_static_hosts: "{{ (image_network_static_hosts|default([])) +
                                     [dict(ip=hostvars[item].ansible_host, name=(item.split('.')[0]|lower))] }}"
      loop: "{{ groups['all'] }}"

  roles:
    - role: rembik.kickstart_iso
      vars:
        image_network_bootproto: 'static'
        image_network_static_netmask: '255.255.252.0'
        image_network_static_gateway: '10.0.0.1'
        image_network_static_nameserver:
          - '10.0.2.1'
          - '10.0.3.1'
```

To run any of the above sample playbooks create a `playbook.yml` file and paste the contents.
Executing the Ansible Playbook is then as simple as executing `ansible-playbook playbook.yml`.

License
-------

[Apache License, Version 2.0](https://github.com/rembik/ansible-role-kickstart-iso/blob/master/LICENSE)

Author Information
------------------

This role was created in 2019 by Brian Rimek.
