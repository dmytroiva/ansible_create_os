# Ansible Create OS

This repository contains the necessary tools to generate a custom Debian image using Ansible. It is designed to automate the process of creating an operating system image, allowing for consistent and reproducible builds.

<span style="color:red;">Attention! This project under development works only for Debian 12</span>
## Features

- Automated Debian image generation with pre-configured settings.
- Preseed configuration for non-interactive installation.
- Customizable settings for hostname, network configuration, and more.
- Integration with GitHub for version control and collaboration.

## Getting Started

To clone the project and start generating your Debian image, follow these steps:

1. Install Ansible on your system.
2. Clone this repository:
git clone https://github.com/dmytroiva/ansible_create_os.git
3. Navigate to the project directory:
cd ansible_create_os
4. Customize: 
- the preseed.cfg file according to your requirements. - download_debian_online.yml to change your home director.
-  change debian version if the play ***'Перевірка URL перед завантаженням Debian-iso'*** will not pass.
5. Run the Ansible playbook to generate the Debian image:
`ansible-playbook download_debian_online.yml -e ip_host=localhost"`
6. 

## Dependencies

- Ansible
- A Debian-based system or compatible environment for image generation
- Access to Debian package repositories or a local mirror

## Customization

Edit the preseed.cfg file to set up your network, user accounts, and package selections. You can specify your hostname, domain, and static IP configuration in this file.

## Example Usage

After configuring your preseed.cfg, generate the image with the following command:

```bash
ansible-playbook download_debian_online.yml -e "ip_host=localhost"
Введіть версію Debian (1 для 9, 2 для 10, 3 для 12): 3

PLAY [Створення та налаштування Debian VM] ****************************************************************************************************************************

TASK [Gathering Facts] ************************************************************************************************************************************************
ok: [localhost]

TASK [get the username running the deploy] ****************************************************************************************************************************
changed: [localhost]

TASK [Генерація URL для завантаження образу Debian] *******************************************************************************************************************
ok: [localhost]

TASK [Створення каталогу для зберігання ISO] **************************************************************************************************************************
ok: [localhost]

TASK [Перевірка URL перед завантаженням Debian-iso] *******************************************************************************************************************
ok: [localhost]

TASK [Завантаження образу Debian, якщо URL дійсний] *******************************************************************************************************************
ok: [localhost]

TASK [Встановлення необхідних утиліт] *********************************************************************************************************************************
ok: [localhost]

TASK [Розпакування завантаженого ISO образу Debian] *******************************************************************************************************************
changed: [localhost]

TASK [Зробити Automated Install Debian стандартним пунктом меню] ******************************************************************************************************
changed: [localhost]

TASK [Додати пункт Automated Install Debian в txt.cfg] ****************************************************************************************************************
changed: [localhost]

TASK [Змінити тайм-аут у всіх cfg файлах в каталозі isolinux] *********************************************************************************************************
changed: [localhost] => (item=txt.cfg)
changed: [localhost] => (item=menu.cfg)
changed: [localhost] => (item=adtxt.cfg)
changed: [localhost] => (item=adgtk.cfg)
changed: [localhost] => (item=rqtxt.cfg)
changed: [localhost] => (item=rqgtk.cfg)
changed: [localhost] => (item=isolinux.cfg)
changed: [localhost] => (item=prompt.cfg)

TASK [Очищення файлів конфігурації меню] ******************************************************************************************************************************
changed: [localhost] => (item=adspkgtk.cfg)
changed: [localhost] => (item=adtxt.cfg)
changed: [localhost] => (item=rqtxt.cfg)
changed: [localhost] => (item=rqspkgtk.cfg)
changed: [localhost] => (item=spkgtk.cfg)

TASK [Видалення пункту 'Install with speech synthesis' з grub.cfg] ****************************************************************************************************
changed: [localhost]

TASK [Генерація preseed файлу з шаблону] ******************************************************************************************************************************
changed: [localhost]

TASK [Створення образу з автовстановленням] ***************************************************************************************************************************
changed: [localhost]

TASK [Зміна власника для директорії "/home/dmytro/debian-auto-install-image-building"] ********************************************************************************
changed: [localhost]

TASK [Видалення тимчасової директорії] ********************************************************************************************************************************
changed: [localhost]

PLAY RECAP ************************************************************************************************************************************************************
localhost                  : ok=17   changed=11   unreachable=0    failed=0    skipped=0    rescued=0    ignored=0  
```

This will start the process of creating a Debian image based on the specifications you've provided.

Contribution
Feel free to fork the project, make your changes, and submit a pull request. We appreciate your contributions to improve the project!

License
This project is open source and available under the MIT License.

All rights reserved by Dmytro Ivanov.