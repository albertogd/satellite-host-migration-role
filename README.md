# satellite-host-migration-role
Ansible role to migrate hosts from an old Satellite to a new Satellite

Migrate your hosts from an old Satellite to a new Satellite using Ansible. This role deregisters the hosts and remove them from Satellite. Then it generates the Registration command, and registers every host to the new Satellite.

# Ansible role for Satellite Registration Command
This role is based on the "Ansible role for Satellite Registration Command": https://github.com/andrewlinuxadmin/ansible-role-satellite-registration-command
