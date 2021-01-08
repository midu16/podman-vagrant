# Description

This is a ```Vagrantfile``` to spawn an podman environment ready to be used.

# Software dependencies

- Vagrant : 2.2.9
- VirtualBox: Version 6.1.16 r140961 (Qt5.6.3)

# Vagrant cli

$ vagrant up 		- for building the VM

$ vagrant ssh		- for log-in into the ssh of the VM. the hosting machine ssh-key has been copied to the target machine.

$ vagrant destroy 	- for terminate the VM

# Pre-requisites

- The VM root user will be accessible after the ```vagrant ssh```connection after using the ```sudo -i```cli command.
- ```vagrant``` user is the system user with limit permissions.
- 

# Contact
Mihai I - 2020 idumihai16@gmail.com


