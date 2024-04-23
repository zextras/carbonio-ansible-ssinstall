# carbonio-ansible-ssconfig
An ansible playbook to install  and optimize a Carbonio Single Server installation.
This playbook imports the following playbook - https://github.com/zextras/carbonio-install-ansible to install a single server 

Run the following command to install and configure the Carbonio single server:

```
ansible-playbook -i inventoryname carbonio-ssreconfig.yml  --extra-vars "install_path=/path/to/carbonio-install-ansible/carbonio-install/carbonio-install.yml"
```
*install_path - this variable should contain the path to the ansible playbook for Carbonio installation