# k8s-ansible-deploy
# Kubernetes Ansible Deployment on RHEL9

This repository contains an Ansible playbook designed to set up an Ansible user and install Kubernetes prerequisites on RHEL9 systems. The playbook automates the installation and configuration of necessary packages and system settings to prepare a RHEL9 machine for Kubernetes deployment.

## Playbook Overview

The playbook performs the following tasks:

1. **Update System Packages**: Ensures all system packages are updated to their latest versions.
2. **Create Ansible User**: Creates an Ansible user with a specified password and adds it to the 'wheel' group for administrative privileges.
3. **Configure Sudoers**: Modifies the sudoers file to allow passwordless sudo access for the 'wheel' group.
4. **Add Kubernetes Repository**: Configures the Kubernetes repository for package installation.
5. **Install Kubernetes Packages**: Installs essential Kubernetes packages including `kubelet`, `kubeadm`, `kubectl`, and `docker`.
6. **Enable Docker Service**: Enables and starts the Docker service.
7. **Disable SELinux**: Disables SELinux for compatibility with Kubernetes.
8. **Disable Swap**: Disables swap and ensures it remains disabled on boot.
9. **Configure Sysctl Parameters**: Sets sysctl parameters for Kubernetes networking requirements.

## Prerequisites

- A RHEL9 system with SSH access.
- Ansible installed on your control machine.

## Installation of Ansible

To install Ansible on your control machine, follow these steps:

1. **Update your package index**:
   ```bash
   sudo yum update -y

2. **Install EPEL repository**:
   ```bash
    sudo yum install epel-release -y

3. **Install Ansible**:
    ```bash
   sudo yum install ansible -y

4. **Running the Playbook**
   ```bash
   Clone the repository:
    git clone <repository-url>
    cd k8s-ansible-deploy

Edit the Inventory File: Create or edit an inventory file to specify the target hosts.
Run the Playbook:
   `ansible-playbook -i <inventory_file> k8s-deploy.yaml`

Replace <inventory_file> with the path to your Ansible inventory file.

Notes
Ensure that the target hosts are accessible via SSH and have the necessary permissions for Ansible operations.
The playbook is designed for RHEL9 systems and may require modifications for other distributions.

License
This project is licensed under the MIT License 
- see the LICENSE file for details.ansible-playbook -i <inventory_file> k8s-deploy.yaml
ansible-playbook -i <inventory_file> k8s-deploy.yaml
