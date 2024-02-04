# Ansible Create OS

This repository contains the necessary tools to generate a custom Debian image using Ansible. It is designed to automate the process of creating an operating system image, allowing for consistent and reproducible builds.

## Features

- Automated Debian image generation with pre-configured settings.
- Preseed configuration for non-interactive installation.
- Customizable settings for hostname, network configuration, and more.
- Integration with GitHub for version control and collaboration.

## Getting Started

To clone the project and start generating your Debian image, follow these steps:

1. Install Ansible on your system.
2. Clone this repository:
git clone https://github.com/yourusername/ansible_create_os.git
3. Navigate to the project directory:
cd ansible_create_os

4. Customize the preseed.cfg file according to your requirements.
5. Run the Ansible playbook to generate the Debian image:
ansible-playbook playbook.yml

## Dependencies

- Ansible
- A Debian-based system or compatible environment for image generation
- Access to Debian package repositories or a local mirror

## Customization

Edit the preseed.cfg file to set up your network, user accounts, and package selections. You can specify your hostname, domain, and static IP configuration in this file.

## Example Usage

After configuring your preseed.cfg, generate the image with the following command:

```bash
ansible-playbook playbook.yml
This will start the process of creating a Debian image based on the specifications you've provided.

Contribution
Feel free to fork the project, make your changes, and submit a pull request. We appreciate your contributions to improve the project!

License
This project is open source and available under the MIT License.

All rights reserved by Dmytro Ivanov.