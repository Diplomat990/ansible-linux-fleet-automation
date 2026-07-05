# Ansible Linux Fleet Automation

This project simulates a real-world Linux infrastructure support task where an engineer manages multiple Linux servers using Ansible.

## Scenario

A Linux support engineer is assigned a change ticket to validate connectivity, manage users, patch servers, check services, harden SSH, configure firewall rules and collect evidence.

## Lab Environment

| Server | Role |
|---|---|
| ansible-control | Ansible control node |
| web01 | Web server |
| db01 | Database server |
| nas01 | NAS/File server |

## Skills Demonstrated

- Ansible automation
- Linux server administration
- SSH access management
- Sudo/become privilege escalation
- Inventory management
- Connectivity testing
- Git and GitHub documentation
- RHEL-compatible Linux administration

## First Test: Ansible Ping

Command used:

```bash
ansible -i inventory/hosts.ini linux_servers -m ping --ask-become-pass
