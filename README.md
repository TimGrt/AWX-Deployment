# AWX Deployment

[![Ansible Lint](https://github.com/TimGrt/AWX-on-Minikube/actions/workflows/ci.yml/badge.svg)](https://github.com/TimGrt/AWX-on-Minikube/actions/workflows/ci.yml) [![CodeFactor](https://www.codefactor.io/repository/github/timgrt/awx-on-minikube/badge)](https://www.codefactor.io/repository/github/timgrt/awx-on-minikube)

The Ansible content in this repository deploys AWX on Kubernetes, by default on a single-node Kind-Cluster.

> [!NOTE]
> The content is tested and developed with Ubuntu 24.04+ on WSL.

> [!IMPORTANT]
> **The AWX deployment is for testing purposes only!**
> **Do not use this in production!**

## Requirements

A managed node with sufficient CPU and memory resources is necessary, at least:

* 4 Cores
* 6-8 GB RAM

Install necessary Galaxy requirements:

```bash
ansible-galaxy collection install -r requirements.yml
```

Install necessary Python requirements:

```bash
pip3 install -r requirements.yml
```

## Usage

After installing all requirements, run the `awx_deployment.yml` playbook.

```bash
ansible-playbook awx_deployment.yml
```

The playbook will output further instructions.
