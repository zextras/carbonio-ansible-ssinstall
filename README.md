# Carbonio single server installation Ansible Playbook
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

Please note that the Carbonio Single Server installation differs from the standard installation. Carbonio Single Server does not support certain components, so carefully review the inventory below before creating and using it:

```
[postgresServers]
srv1.example.com

[masterDirectoryServers]
srv1.example.com

[serviceDiscoverServers]
srv1.example.com

[dbsConnectorServers]
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

############ These Roles are not supported in Single-Server scenario ###########
############ They are required for the proper Ansible installation #############

[replicaDirectoryServers]

[prometheusServers]

[syslogServer]

```