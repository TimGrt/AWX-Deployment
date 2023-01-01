# AWX in Minikube

[![Ansible Lint](https://github.com/TimGrt/AWX-on-Minikube/actions/workflows/ci.yml/badge.svg)](https://github.com/TimGrt/AWX-on-Minikube/actions/workflows/ci.yml) [![CodeFactor](https://www.codefactor.io/repository/github/timgrt/awx-on-minikube/badge)](https://www.codefactor.io/repository/github/timgrt/awx-on-minikube)

This playbook installs AWX on a Minikube instance running on an Ubuntu host.

## Requirements

A managed node with sufficient CPU and memory resources is necessary, at least:

* 4 Cores
* 6-8 GB RAM

Run the `check-requirements.yml` playbook to ensure that your Ansible Controller has all required Collections and Python packages installed.  

Install necessary Galaxy requirements:

```bash
ansible-galaxy collection install -r requirements.yml
```

Install necessary Python requirements:

```bash
pip3 install -r requirements.yml
```

Adjust the inventory.  
The playbook needs *sudo* permissions, either set an appropriate user or use the `bootstrap.yml` playbook which prepares the managed node.  

Run the playbook and provide a user which can access the managed node and has root permissions, a dedicated *ansible* user with sudo permissions is created and all packages are updated to latest state.
```bash
ansible-playbook bootstrap.yml -e ansible_user=<default-user> --ask-pass --ask-become-pass
```

## Usage

After installing all requirements, run the `main.yml` playbook.

```bash
ansible-playbook main.yml
```

The playbook will output further informations.
