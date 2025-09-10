# Changelog

All notable changes to this project will be documented in this file. 

### [25.9.0] (2025-9-10)

### Features
* Updated version and version of dependencies (carbonio-install-ansible --> 25.9.0)
* Replaced deprecated Ansible module `postgresql_set` with `postgresql_alter_system`  (ensures forward compatibility with community.postgresql ≥ 5.0, removes deprecation warnings)
* Since config.ini became optional, added a configuration file for single server

### [25.6.0] (2025-5-21)

### Features
* Updated version and version of dependencies (carbonio-install-ansible --> 25.6.0)
* Changed WSC host for the installation, check updated README or inventory file

### [25.3.5] (2025-4-10)

### Features
* Updated version of dependencies (carbonio-install-ansible --> 25.3.3)

### [25.3.4] (2025-3-19)

### Features
* Updated version of dependencies (carbonio-install-ansible --> 25.3.2)

### [25.3.3] (2025-3-19)

### Features
* Implemented to stop and disable services instead of masking

### [25.3.2] (2025-3-19)

### Bug Fixes
* Added condition to stop needed sidecars only on main single server node
* Fixed conditions for postgres restart 

### [25.3.1] (2025-3-19)

### Bug Fixes
* Fixed typo in conditions for execute-carbonio-reconfig

### [25.3.0] (2025-3-14)

### Bug Fixes
* Fixed typo in conditions for execute-carbonio-reconfig

### [25.3.0] (2025-3-14)

### Features
* Added WSC installation support
* Updated version of dependencies (carbonio-install-ansible --> 25.3.0)

### Bug Fixes
* Fixed issue to install optional roles on a different VMs (added conditions to configure only right groups).


# Changelog

All notable changes to this project will be documented in this file. 