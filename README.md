# Ansible Linux Fleet Automation and Patching Lab

## Project Overview

This project simulates a real-world Linux infrastructure support task where a Linux engineer manages multiple RHEL-compatible servers using Ansible.

The lab focuses on automation, user management, SSH access, patching, service validation, hardening, reporting and GitHub-based documentation.

## Scenario

A Linux support engineer is assigned a change ticket to validate connectivity, create a standard admin account, prepare SSH key-based access, patch servers, check critical services, harden SSH, configure firewall rules and collect evidence.

## Lab Environment

| Server          | Role                 | Purpose                         |
| --------------- | -------------------- | ------------------------------- |
| ansible-control | Ansible control node | Runs Ansible playbooks          |
| web01           | Web server           | Simulates Nginx/Apache workload |
| db01            | Database server      | Simulates MariaDB workload      |
| nas01           | NAS/File server      | Simulates Samba/NFS workload    |

## Architecture

```text
Windows Host / VirtualBox
        |
        | SSH
        |
ansible-control
        |
        | Ansible automation
        |
--------------------------------
| web01 | db01 | nas01 |
--------------------------------
```

## Tools Used

* AlmaLinux / RHEL-compatible Linux
* Ansible
* SSH
* Bash
* Git and GitHub
* firewalld
* SELinux
* systemd
* sudo/wheel group
* VirtualBox

## Skills Demonstrated

* Linux server administration
* Ansible inventory management
* Ansible playbook execution
* SSH access management
* SSH key-based authentication
* User and sudo management
* Privilege escalation using sudo/become
* GitHub documentation
* Evidence-based infrastructure work

## Playbooks Created

| Playbook             | Purpose                                                       |
| -------------------- | ------------------------------------------------------------- |
| `01-ping.yml`        | Validates Ansible connectivity to all managed Linux servers   |
| `02-users.yml`       | Creates a standard Linux admin user and configures SSH access |
| `03-patching.yml`    | Planned patching automation                                   |
| `04-services.yml`    | Planned service validation                                    |
| `05-hardening.yml`   | Planned SSH/firewall hardening                                |
| `06-logs-report.yml` | Planned log collection and reporting                          |
| `07-site.yml`        | Planned full automation run                                   |

## 01 - Ansible Connectivity Test

Command used:

```bash
ansible -i inventory/hosts.ini linux_servers -m ping --ask-become-pass
```

Result:

All managed nodes returned `pong`, confirming Ansible connectivity.

### Screenshot Evidence

![Ansible Ping Success](screenshots/ansible-ping-success.png)

## 02 - User Management Playbook

Playbook used:

```bash
ansible-playbook -i inventory/hosts.ini playbooks/02-users.yml -u root -k
```

The `02-users.yml` playbook creates a standard Linux admin account called `linuxadmin` across all managed servers.

### What the playbook does

* Creates the `linuxadmin` user
* Sets `/bin/bash` as the default shell
* Adds the user to the `wheel` group for sudo access
* Creates `/home/linuxadmin/.ssh`
* Copies the Ansible control node public SSH key into `authorized_keys`
* Creates a sudoers file for `linuxadmin`

### Why this matters

This simulates a real Linux administration task where a support engineer creates a controlled admin account, configures SSH key-based access and prepares the account for secure remote management.

### Screenshot Evidence

![User Management Playbook](screenshots/ansible-users-playbook.png)

## How to Run

Clone the repository:

```bash
git clone https://github.com/Diplomat990/ansible-linux-fleet-automation.git
cd ansible-linux-fleet-automation
```

Test connectivity:

```bash
ansible -i inventory/hosts.ini linux_servers -m ping
```

Run the connectivity playbook:

```bash
ansible-playbook -i inventory/hosts.ini playbooks/01-ping.yml
```

Run the user management playbook:

```bash
ansible-playbook -i inventory/hosts.ini playbooks/02-users.yml -u root -k
```

## Security Notes

Passwords and private SSH keys are not stored in this repository.

The project is designed to move from temporary root/password access to a more secure model using:

```text
linuxadmin + SSH key authentication + sudo
```

## Ticket Simulation

Ticket ID: `CHG-LNX-001`

Task: Validate Linux server connectivity and create a standard admin account for secure Ansible management.

Acceptance criteria:

* All managed servers are reachable by Ansible
* `linuxadmin` account exists on all servers
* `linuxadmin` has sudo access
* SSH key-based access is configured
* Evidence screenshots are uploaded to GitHub

## Rollback Plan

If the user creation task fails:

1. Login to the affected server as root.
2. Remove the user if required:

```bash
userdel -r linuxadmin
```

3. Remove sudoers file if required:

```bash
rm -f /etc/sudoers.d/linuxadmin
```

4. Re-run the playbook after fixing the issue.

## Lessons Learned

* Ansible requires working SSH access before playbooks can run.
* Ping success confirms network access, but SSH authentication must also be configured correctly.
* Password authentication and SSH key authentication behave differently.
* GitHub documentation should include screenshots, playbooks, commands and evidence.
* Empty folders do not appear in GitHub unless they contain a file such as `.gitkeep`.

## Project Status

| Phase                    | Status      |
| ------------------------ | ----------- |
| GitHub repo created      | Complete    |
| Inventory created        | Complete    |
| Ansible ping tested      | Complete    |
| User management playbook | Complete    |
| Patching playbook        | In progress |
| Services validation      | Planned     |
| Hardening                | Planned     |
| Reporting                | Planned     |






