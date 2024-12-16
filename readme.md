# AKS LAMP Stack Deployment with Ansible

This repository contains Ansible playbooks and roles to create an Azure Kubernetes Service (AKS) cluster and deploy a LAMP stack (Linux, Apache, MySQL, PHP) on it.

## Repository Structure

- `ansible.cfg`: Configuration file for Ansible.
- `hosts`: Inventory file specifying the target hosts.
- `main.yaml`: Main playbook to create the AKS cluster and deploy the LAMP stack.
- `roles/`: Directory containing Ansible roles.
  - `create_aks/`: Role to create the AKS cluster.
    - `tasks/main.yml`: Tasks to create the AKS cluster.
    - `vars/main.yml`: Variables for the AKS cluster creation.
  - `deploy_lamp/`: Role to deploy the LAMP stack.
    - `tasks/main.yml`: Tasks to deploy the LAMP stack.
    - `vars/main.yml`: Variables for the LAMP stack deployment.
    - `files/`: Directory containing Kubernetes resource files.
      - `mysql-deployment.yml`: Deployment configuration for MySQL.
      - `mysql-pvc.yml`: Persistent Volume Claim for MySQL.
      - `mysql-service.yml`: Service configuration for MySQL.
      - `nginx-php-deployment.yml`: Deployment configuration for Nginx with PHP.
      - `nginx-service.yml`: Service configuration for Nginx with PHP.

## Prerequisites

- An Azure account with sufficient permissions to create resources.
- Ansible installed on your local machine.
- Azure CLI installed and configured on your local machine.

## Usage

1. Clone the repository:
2. Update the variables in roles/create_aks/vars/main.yml and roles/deploy_lamp/vars/main.yml as needed.
3. Log in to Azure using the Azure CLI:
```bash
az login
```
4. Run the playbook to create the AKS cluster and deploy the LAMP stack:
```bash
ansible-playbook main.yaml
```
After the playbook completes, the URL of the deployed website will be displayed.