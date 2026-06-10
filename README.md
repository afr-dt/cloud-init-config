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
- **Infrastructure**: Terraform, Ansible, Helm.
- **Cloud CLIs**: AWS CLI v2, Google Cloud CLI (gcloud).
- **AI CLIs**: Antigravity CLI (agy), OpenCode CLI.
- **Kubernetes**: kubectl, k9s, kubectx, kubecolor (aliased to kubectl).
- **Utilities**: JQ, fzf, htop, tmux, unzip, curl, git, fastfetch.
- **Editor**: Neovim (configured with LazyVim).
- **Shell**: Zsh (Powerline fonts support) with **Starship Prompt**.

## 🏁 Getting Started

### 1. Prerequisites
Ensure [Multipass](https://multipass.run/install) is installed on your system.

### 2. Launch the Instance
Run one of the following commands from the project root. We recommend specifying resource limits to prevent the VM from consuming too many host resources:

**Latest LTS (Recommended):**
```bash
multipass launch lts \
  --name devops-instance \
  --cpus 2 \
  --memory 4G \
  --disk 20G \
  --cloud-init ./cloud-config.yaml
```

**Specific Version (e.g., 24.04):**
```bash
multipass launch 24.04 \
  --name devops-instance \
  --cpus 2 \
  --memory 4G \
  --disk 20G \
  --cloud-init ./cloud-config.yaml
```

#### 💡 Resource Customization
Since hardware resources are managed by the host's hypervisor, they must be specified during launch:
- `--cpus <count>`: Number of CPU cores (default: 1).
- `--memory <size>`: RAM allocation (e.g., `4G`, `2048M`, default: 1G).
- `--disk <size>`: Total disk space (e.g., `20G`, `50G`, default: 5G).

#### 💡 Specifying Ubuntu Versions
You can customize the Ubuntu release by providing the version number or codename as the first argument to `multipass launch`.
- Use `multipass find` to see all available images.
- Common aliases: `lts` (latest), `noble` (24.04), `jammy` (22.04).

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
