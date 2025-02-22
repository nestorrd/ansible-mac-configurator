# Ansible Mac Configurator

This repository contains Ansible playbooks and roles for configuring a macOS system using Homebrew.

## Directory Structure

- **roles/**: Contains reusable roles.
  - **homebrew/**: A role that includes tasks and variables for managing Homebrew.
    - **tasks/**: Contains the main tasks for the role.
      - `main.yml`: The main task file.
    - **vars/**: Role-specific variables.
      - `main.yml`: Variables for the homebrew role.

- **playbooks/**: Contains playbooks for executing tasks.
  - `configure.yml`: The main playbook for configuring the macOS system.

- `ansible.cfg`: Configuration file for Ansible settings.
- `LICENSE`: License file for the repository.
- `README.md`: Documentation for the repository.

## Usage

1. Fork the repository and clone it.
2. This repository needs a `vars.yml` file where you will store your desired configuration. In case you want to push your changes, remove `vars.yml` from `.gitignore` and make your repository Private.
3. Create a `vars.yml` file in the `playbooks` directory with the desired content:
   ```yaml
   homebrew_packages:
     - name: your_package

   homebrew_cask_packages:
     - name: your_cask_package
       sudo_password: "{{ password }}"
4. Run the playbook using the command:
   ```sh
   ansible-playbook /path/to/repo/playbooks/configure.yml