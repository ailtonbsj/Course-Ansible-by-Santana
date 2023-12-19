# Course of Ansible by Mário Santana
![](https://img.shields.io/badge/status-progress-blue)

<p align="center">
<img src=".github/logo.png">
</p>

Learning Ansible with an [Youtube playlist](https://youtube.com/playlist?list=PLORF-y_edVoDQnky9u2OgyrfirE1dhutX&si=Dnfs1d_0f1k4_AFE).

Creator Mário Santana

## History of commands

Using `VS Code` with extension `Remote - SSH`:

```bash
ext install ms-vscode-remote.remote-ssh
```

Installing ansible on Ubuntu/debian:

```bash
sudo apt install python3-pip
sudo apt install pipx
pipx ensurepath
pipx install --include-deps ansible
```

Working with SSH keys:

```bash
# Generate ssh key pair  on ~/.ssh/
ssh-keygen

# Copy public key for another host
ssh-copy-id username@hostname.domain
```

### CentOS 9 Commands

```bash
# Add user to use sudo
usermod -aG wheel username

# Add to END of sudoers file
# username  ALL=(ALL) NOPASSWD:ALL
# username ALL=(ALL) NOPASSWD:/usr/bin/du,/usr/bin/ping
visudo
```

### Ansible Commands

```bash
# Test if ansible is working
ansible localhost -m ping

# Check version and confs
ansible --version

# Ping per group name
ansible someGroupName -m ping

# Ping all machines
ansible all -m ping

# Install package on demand
ansible ubuntu -m apt -a "name=curl state=present" --become

# Remove package on demand
ansible ubuntu -m apt -a "name=curl state=absent" --become

# Get lots of informations about machines
ansible all -m setup

# Get information filtered
ansible all -m setup -a "filter=ansible_distribution_file_variety"
ansible all -m setup -a "filter=ansible_distribution"

# Run a playbook
ansible-playbook playbook-01.yml

# Create roles
ansible-galaxy init serverTools
ansible-galaxy init mysql
```
