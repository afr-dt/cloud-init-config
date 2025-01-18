# Ubuntu Cloud-Init Instance with DevOps Tools for Multipass

This repository provides a pre-configured Ubuntu cloud-init instance with essential DevOps tools, designed to be used with Multipass. 

## Features
- **Multipass Compatibility:** Easily deployable with Multipass for quick and lightweight virtual machines.
- **Pre-installed Tools:** Includes popular DevOps tools like Docker, Kubernetes CLI, Terraform, Ansible, and more.
- **Automated Setup:** Cloud-init automates the installation and configuration process.
- **Lightweight and Scalable:** Ideal for local development, testing, and CI/CD pipelines.

## Getting Started
1. **Install Multipass:** Ensure Multipass is installed on your system.
2. **Launch the instance:**
   ```bash
   multipass launch --name devops-instance --cloud-init ./cloud-init.yaml
