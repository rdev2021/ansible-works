# Raspberry Pi Setup with Ansible

Personal project for Ansible to automate the setup, configuration, and ongoing maintenance of a suite of Raspberry Pi devices. Ideal for my use case to manage multiple Raspberry Pi nodes, this project streamlines updates, package installations, and configuration tasks across all devices from a central machine.

## Features

- **Automated OS Updates**: Keeps Raspberry Pi devices up-to-date with the latest software and security patches.
- **Software Installation**: Installs essential software packages (e.g., Python, Docker, Git) across all Raspberry Pis.

  ### TODO
    - **Custom Configurations**: Configures system settings, network configurations, and other parameters specific to each device.
    - **User Management**: Creates and manages user accounts as needed.

## Requirements

- **Ansible 2.9+**: Ensure Ansible is installed on your control machine.
- **Inventory File**: Define all Raspberry Pi IPs in the Ansible inventory file.
- **SSH Access**: SSH key-based access to each Raspberry Pi for passwordless configuration.

## Setup

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/rdev2021/ansible-works.git
   cd ansible-works
   ```

2. **Edit Inventory File**: Update the inv.ini file with the IP addresses (or hostname ) of your Raspberry Pi devices.

3. **Configure Variables**: Customize inv.yml for desired settings, like packages to install and custom configurations.

## Usage

- **Run Playbooks:**
    - **Setup Raspberry Pis:**
        ```bash
        ansible-playbook -i inv.yml rasp-setup.yml -vv
        ```
    - **Update Raspberry Pi Suite:**
        ```bash
        ansible-playbook -i inv.yml rasp-update.yml -vv
        ```
    - **Check Connectivity:**
        ```bash
        ansible -i inv.yml -m ping
        ```

## Playbooks
- **rasp-setup.yml:** Initializes each Raspberry Pi with basic settings, packages, and configurations.
- **rasp-update.yml:** Updates OS packages and applies any new configurations to all devices.
