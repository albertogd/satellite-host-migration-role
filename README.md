# Ansible role for Host Migration

Migrate your hosts from an old Satellite to a new Satellite using Ansible.

## Worflow

The steps followed by the role are:

1. Exports as facts and create a backup in a temp folder of all the useful content hosts information:
   * Organization name
   * Location name
   * Lifecycle Environment name
   * Activation Key
   * Operating System name
   * Repository names
1. Unregisters the hosts from the old Satellite and uninstall the *old Satellite* `katello-ca-consumer`
1. Install the *new Satellite* `katello-ca-consumer`
1. It gets all the `content IDs` in the new Satellite:
   * Organization name
   * Location name,
   * Lifecycle Environment ID
   * Operating System ID 
1. It generates the Registration command for each host (with its own content), registers every host to the new Satellite, and enable all the repositories.

## Requirements

This role depends on the collection `community.general`.

### Connected environment

Install the collection using ansible-galaxy install

```shell
ansible-galaxy collection install community.general
```

### Disconnected environment

Download the collection in a connected environment:

```shell
wget https://galaxy.ansible.com/download/community-general-7.1.0.tar.gz
```

Copy the tar file to your disconnected environment, and extract the collection in the path `$HOME/.ansible/collections/ansible_collections/`.

## Tests

This role has been tested migrating RHEL 6, 7 and 8 hosts

## Ansible role for Satellite Registration Command

This role is based on the "Ansible role for Satellite Registration Command": https://github.com/andrewlinuxadmin/ansible-role-satellite-registration-command
