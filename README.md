# Carbonio single server installation Ansible Playbook
An ansible playbook to install and optimize a Carbonio Single Server installation.
This playbook imports the following playbook - https://github.com/zextras/carbonio-install-ansible to install a single server 

This playbook imports the Carbonio installation playbook automatically in carbonio-asible-ssinstall and here you have 2 options:

 if you need to use Release Candidate version of Carbonio, then you need to clone carbonio-install-ansible playbook for installation and go to the rc branch. Return to carbonio-ansible-ssinstall and run with local path of the installation playbook”

```
ansible-playbook -i inventoryname playbooks/carbonio_ssinstall.yml  --extra-vars "install_path=/path/to/carbonio-install-ansible/carbonio-install/carbonio-install.yml"
```

If you need the Release version of Carbonio, then you can simply use Ansible Galaxy, install the collection, specify the playbook from the collection in the path and run the command:

```
#Install the collection 
ansible-galaxy collection install zxbot.carbonio_install

#Install and configure a single server
ansible-playbook -i inventoryname playbooks/carbonio_ssinstall.yml  --extra-vars "install_path=zxbot.carbonio_install.carbonio_install"
```

*install_path - this variable should contain the path to the ansible playbook for Carbonio installation
