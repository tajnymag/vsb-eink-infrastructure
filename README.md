# VŠB E-Ink - Orchestrace služeb cloudového prostředí

## Description

The repository contains Ansible playbooks for provisioning and configuring the primary cloud environment for the VŠB E-Ink project.
The playbooks are designed to be run on a local machine with Ansible installed.

Currently, the main playbook is `site.yml` which sets up the following:

* firewall rules
* **docker** with necessary authentication to our private registry
* **traefik** as a reverse proxy
* **portainer** for web managment of docker containers (subject to change)
* **watchtower** for automatic updates of docker containers
* **eink-gateway** - our service for handling communication between the e-ink display and the cloud

## Requirements

* ansible

## Deployment

1. Create a file `vault_pass.txt` in the root of the repository and put our vault password there
2. Ensure you have ssh access to the target hosts
3. Run `ansible-playbook site.yml`