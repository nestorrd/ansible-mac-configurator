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
2. Create a **private** repository, where you will store your own configuration. This is needed to keep your configuration private.
3. Update `vars/custom_vars.yml` to point to your local copy of the private repository.
4. Create a file in your private repository named `private_vars.yml`. In here you will add all needed configuration used by roles. The file should look like this:
   ```yaml
   homebrew_packages:
     - name: your_package

   homebrew_cask_packages:
     - name: your_cask_package
       sudo_password: "{{ password }}"
5. [Optional] Create or store your own `.zshrc` zsh configuration file in your private repository. This is optional, in case you don't have any yet, it will be created during installation.
6. Run the playbook using the command:
   ```sh
   ansible-playbook /path/to/repo/playbooks/configure.yml
7. Push your changes to your private repository to keep your configuration safe.