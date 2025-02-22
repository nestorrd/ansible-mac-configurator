# Ansible Mac Configurator

This repository contains Ansible playbooks and roles for configuring a macOS system using Homebrew.

## Directory Structure

- **roles/**: Contains reusable roles.
  - **homebrew/**: A role that includes tasks and variables for managing Homebrew.
    - **tasks/**: Contains the main tasks for the role.
      - `main.yml`: The main task file.

- **playbooks/**: Contains playbooks for executing tasks.
  - `configure.yml`: The main playbook for configuring the macOS system.

- `ansible.cfg`: Configuration file for Ansible settings.
- `LICENSE`: License file for the repository.
- `README.md`: Documentation for the repository.

## Usage

1. Clone the repository.
2. Create a **private** repository (the repo as it is looks for `ansible-mac-configurator-private`, but change it for the one you created), where you will store your configuration in a yaml file (the repo as it is looks for `private_vars.yml`). This is needed to keep your configuration private.
2. In this file you will store your desired configuration. As an example:
   ```yaml
   homebrew_packages:
     - name: your_package

   homebrew_cask_packages:
     - name: your_cask_package
       sudo_password: "{{ password }}"
4. Run the playbook using the command:
   ```sh
   ansible-playbook /path/to/repo/playbooks/configure.yml
5. Push your changes to your private repository to keep your configuration safe.