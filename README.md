# Ansible Hardening

This repository contains an Ansible configuration to perform hardening on Ubuntu 20.04 systems, following the CIS Benchmarks guidelines. The project uses Ansible roles and collections to configure and strengthen server security, and includes security assessments with OpenSCAP.

## Project Structure

The repository is organized as follows:

- `/requirements.yml`: Defines the necessary Ansible collections.
- `/group_vars/cis.yml`: Global variables for hardening configuration.
- `/host_vars/desktop1/cis.yml`: Variables specific to the `desktop1` host.
- `/host_vars/master/cis.yml`: Variables specific to the `master` host.
- `/hosts/hosts.yml`: Ansible inventory file.
- `/roles/requirements.yml`: Defines the roles required for the project.
- `/ansible.cfg`: Ansible configuration file.
- `/hardening.yml`: Main playbook to apply hardening.
- `/openscap_report_desktop.yml`: Playbook to perform security assessments with OpenSCAP for desktops.
- `/openscap_report_servers.yml`: Playbook to perform security assessments with OpenSCAP for servers.
- `/poweroff_hosts.yml`: Playbook to power off hosts.
- `/reboot_hosts.yml`: Playbook to reboot hosts.
- `/remediate_desktop.yml`: Playbook to remediate desktop hosts.
- `/remediate_hosts.yml`: Playbook to remediate general hosts.
- `/remediate_master.yml`: Playbook to remediate the master host.
- `/remediate_master_lvl2.yml`: Playbook for advanced remediation of the master host.

## Configuration

1. **Inventory**: The file `awx/hosts/hosts.yml` contains the definition of hosts and host groups.

2. **Variables**: Global variables are in `awx/group_vars/cis.yml`, while host-specific variables are located in `awx/host_vars/`, specifically for `master` and `desktop1`.

## Roles Used

### `cis-hardening`

The `cis-hardening` role is part of the `ansible-lockdown` repository, which applies security recommendations based on CIS benchmarks for Ubuntu systems.

- **Repository**: [ansible-lockdown](https://github.com/ansible-lockdown)
- **Role**: `cis-hardening`
