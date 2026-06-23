# Automated Docker installation across Ubuntu and Amazon Linux 2023 EC2 instances using Ansible.

## Project Structure
```
ansible-docker-automation/
├── inventory.yml           # Host groups for Ubuntu and Amazon Linux
├── docker-playbook.yml     # Docker playbook for Ubuntu
└── Aldocker-playbook.yml   # Docker playbook for Amazon Linux
```
## Steps Followed
- Ansible installed on Master node
- AWS EC2 instances (Ubuntu + Amazon Linux 2023)
- SSH key pair configured
- Docker,Git and other dependencies,packages installed in Master node 

## Usage
```bash
# Run Ubuntu playbook
ansible-playbook -i inventory.yml docker-playbook.yml

# Run Amazon Linux playbook
ansible-playbook -i inventory.yml Aldocker-playbook.yml
```

## Issues Fixed
- curl-minimal conflict on Amazon Linux 2023
- $releasever resolving to full AL2023 version string instead of 9
- RPM-owned packages blocking pip upgrades
- python3-apt missing on fresh Ubuntu nodes
- externally-managed-environment error on Ubuntu 23+

## Tools Used
- Ansible
- AWS EC2
- Docker
- Ubuntu 22/24
- Amazon Linux 2023
