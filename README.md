# Ubuntu DevOps Instance for Multipass

A pre-configured Ubuntu `cloud-init` configuration for [Multipass](https://multipass.run/), optimized for DevOps workflows with pre-installed tools.

## 🚀 Features
- **Multipass Optimized**: One-command deployment of a lightweight Linux VM.
- **Comprehensive DevOps Stack**: Pre-installed cloud, infrastructure, and development tools.
- **Automated Provisioning**: Fully hands-off setup via `cloud-init`.
- **Modern Development Experience**: Includes Zsh, Tmux, and Neovim (LazyVim).

## 🛠 Tools Included
- **Programming**: Go (v1.23.5), Python (v3.13 managed by uv), Node.js (LTS managed by nvm), Build-essential.
- **Python Management**: uv (Astral's fast Python manager).
- **Node.js Management**: nvm (Node Version Manager).
- **Infrastructure**: Terraform.
- **Cloud CLIs**: AWS CLI v2, Google Cloud CLI (gcloud).
- **Kubernetes**: kubectl, k9s.
- **Utilities**: JQ, fzf, htop, tmux, unzip, curl, git.
- **Editor**: Neovim (configured with LazyVim).
- **Shell**: Zsh (Powerline fonts support).

## 🏁 Getting Started

### 1. Prerequisites
Ensure [Multipass](https://multipass.run/install) is installed on your system.

### 2. Launch the Instance
Run the following command from the project root:
```bash
multipass launch --name devops-instance --cloud-init ./cloud-config.yaml
```

### 3. Access the Shell
Once the instance is running, connect to it:
```bash
multipass shell devops-instance
```

### 4. Cleanup
To stop and delete the instance:
```bash
multipass delete --purge devops-instance
```

## ⚙️ Configuration Details
- **User**: `ubuntu`
- **Default Password**: `root`
- **Sudo**: Passwordless sudo is enabled for the `ubuntu` user.
- **Environment**: Custom binaries are added to the system PATH via `/etc/profile.d/custom_path.sh`.
