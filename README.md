# Ansible - Role - Bootstrap Packer Debian image

An Ansible role that can be used to help bootstrap the creation of Debian/Ubuntu server images.

## Requirements

Make sure you are running this on an Ubuntu or Debian based system.

To run this role from your local machine, the following software must be installed/present:
  - [Ansible](http://docs.ansible.com/intro_installation.html)

To test the role using the preconfigured Vagrantfile, the following software must be installed/present on your local system:
  - [Vagrant](http://vagrantup.com/)
  - [VirtualBox](https://www.virtualbox.org/)

## Variables

Available variables are listed below (and in `defaults/main.yml`):

    time_zone: UTC

The `time_zone` variable is used by Ansible to set the time zone of the machine. By default, it is set to UTC.

## Dependencies

None.

## Example Playbook

# Configure your `requirements.yml` to download from the correct role location:

```yaml
---
- src: https://github.com/ajcarberry/ansible-role-packer-debian
  version: master
  name: ajcarberry.packer-debian
```

# Call the role from your playbook or configure it in your `meta/main.yml` file:

**meta/main.yml**
```yaml
---
dependencies:
  - { role: ajcarberry.packer-debian, time_zone: ['UTC'] }
```

**playbook.yml**
```yaml
---
- hosts: all
  become: yes
  gather_facts: yes

  vars:
    time_zone: UTC
  roles:
    - role: ajcarberry.packer-debian
```

## Testing the role

There's an included Vagrantfile that allows quick testing of the Ansible role using a prebuilt Vagrant box. From this same directory, run the following command:

    $ vagrant up

## License

GNU GPL v3

## Author Information

Alex Carberry
