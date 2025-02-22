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

1. Clone the repository.
2. Run the playbook using the command:
   ```sh
   ansible-playbook playbooks/configure.yml