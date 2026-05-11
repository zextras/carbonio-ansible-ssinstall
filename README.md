# Carbonio single server installation Ansible Playbook

> **Deprecated since version 26.6.0**
>
> This playbook is deprecated starting from version `26.6.0`.
> Single-server installation is now supported directly by the official
> `carbonio-install-ansible` playbook:
>
> https://github.com/zextras/carbonio-install-ansible
>
> Use the official `carbonio-install-ansible` playbook for new single server installations.
> This repository is kept only for compatibility with older installation flows.

An ansible playbook to install and optimize a Carbonio Single Server installation.
This playbook imports the following playbook - https://github.com/zextras/carbonio-install-ansible to install a single server 

This playbook imports the Carbonio installation playbook automatically as carbonio_ssinstall dependency.

To install Carbonio Single Server you can simply use Ansible Galaxy: install the collection, specify the playbook from the collection  and run the command:

```
#Install the collection 
ansible-galaxy collection install zxbot.carbonio_ssinstall

#Install and configure a single server
ansible-playbook -i inventoryname zxbot.carbonio_ssinstall.carbonio_ssinstall  --extra-vars "install_path=zxbot.carbonio_install.carbonio_install"
```

*install_path - this variable should contain the path to the ansible playbook for general Carbonio installation (it was installed as dependency)

If default_domain is defined: The bootstrap process will create only this domain as the default/first domain. All system accounts (admin, spam., ham., virus-quarantine., galsync.) will be created under this domain.

If omitted: Falls back to a domain derived from the server's hostname

Please note that the Carbonio Single Server installation differs from the standard installation. Carbonio Single Server does not support certain components, so carefully review the inventory below before creating and using it:

```
[postgresServers]
srv1.example.com

[masterDirectoryServers]
srv1.example.com

# Custom Default Domain (Optional)
[masterDirectoryServers:vars]
#default_domain=domain.com # Replace with your desired domain

[serviceDiscoverServers]
srv1.example.com

[mtaServers]
srv1.example.com

[proxyServers]
srv1.example.com

[proxyServers:vars]
#webmailHostname=mail.example.com

[applicationServers]
srv1.example.com

############ Optional Roles ############

[previewServers]
srv1.example.com

[filesServers]
srv1.example.com


############ Optional Roles - to be installed on a different VM ############
[taskServers]
#srv2.example.com

[docsServers]
#srv2.example.com

[videoServers]
#srv3.example.com public_ip_address=x.y.z.t

[workStreamServers]
#srv2.example.com

############ These Roles are not supported in Single-Server scenario ###########
############ They are required for the proper Ansible installation #############

[dbsConnectorServers]
#Only for HA infrastructure from 24.12.0. Don't fill it out

[replicaDirectoryServers]

[prometheusServers]

[syslogServer]

```