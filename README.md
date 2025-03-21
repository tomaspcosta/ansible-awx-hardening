#   Ansible Hardening

##   Table of Contents

1.  [Project Description](#project-description)
2.  [Technologies Used](#technologies-used)
3.  [Project Structure](#project-structure)
4.  [Playbooks](#playbooks)
5.  [Configuration](#configuration)
6.  [Roles Used](#roles-used)

##   1. Project Description

This repository contains an Ansible configuration to perform hardening on Ubuntu 20.04 systems, following the CIS Benchmarks guidelines. The project uses Ansible roles and collections to configure and strengthen server security and includes security assessments with OpenSCAP.

This project automates the process of securing Ubuntu 20.04 systems by applying industry-standard CIS Benchmarks, ensuring a more secure environment. It leverages Ansible's automation capabilities to streamline the hardening process and includes OpenSCAP for verification and reporting.

##   2. Technologies Used

* Ansible
* CIS Benchmarks
* OpenSCAP

##   3. Project Structure

The repository is organized as follows:

* `/requirements.yml`: Defines the necessary Ansible collections.
* `/group_vars/cis.yml`: Global variables for hardening configuration.
* `/host_vars/desktop1/cis.yml`: Variables specific to the `desktop1` host.
* `/host_vars/master/cis.yml`: Variables specific to the `master` host.
* `/hosts/hosts.yml`: Ansible inventory file.
* `/roles/requirements.yml`: Defines the roles required for the project.
* `/ansible.cfg`: Ansible configuration file.

##   4. Playbooks

The repository includes the following Ansible playbooks:

* **`hardening.yml`**: Main playbook to apply hardening configuration to Ubuntu systems.
* **`openscap_report_desktop.yml`**: Performs security assessments with OpenSCAP for desktop systems.
* **`openscap_report_servers.yml`**: Performs security assessments with OpenSCAP for server systems.
* **`poweroff_hosts.yml`**: Powers off the specified hosts.
* **`reboot_hosts.yml`**: Reboots the specified hosts.
* **`remediate_desktop.yml`**: Applies remediation to desktop hosts.
* **`remediate_hosts.yml`**: Applies remediation to general hosts.
* **`remediate_master.yml`**: Applies remediation to the master host.
* **`remediate_master_lvl2.yml`**: Provides advanced remediation for the master host.
* **`scap_remediation_desktop.yml`**: Generates and applies SCAP remediation for desktop systems.
* **`scap_remediation_master.yml`**: Generates and applies SCAP remediation for the master system.
* **`scap_remediation_servers.yml`**: Generates and applies SCAP remediation for server systems.

##   5. Configuration

* **Inventory**: The file `hosts/hosts.yml` contains the definition of hosts and host groups.
* **Variables**: Global variables are in `group_vars/cis.yml`, while host-specific variables are located in `host_vars/`, specifically for `master` and `desktop1`.

##   6. Roles Used

###   cis-hardening

The `cis-hardening` role is part of the ansible-lockdown repository, which applies security recommendations based on CIS benchmarks for Ubuntu systems.

* **Repository**: ansible-lockdown
* **Role**: cis-hardening
