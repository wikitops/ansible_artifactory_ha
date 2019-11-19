# Ansible : Playbook Jfrog Artifactory HA

The aim of this project is to deploy an highly available Jfrog Artifactory on Vagrant instances with PostgreSQL backend.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

What things you need to run this Ansible playbook :

*   [Vagrant](https://www.vagrantup.com/docs/installation/) must be installed on your computer
*   Update the Vagrant file based on your computer (CPU, memory), if needed
*   Update the operating system to deploy in the Vagrant file (default: Ubuntu)
*   Download the Ansible requirements:

```bash
$ ansible-galaxy install -r requirements.yml
```

### Usage

A good point with Vagrant is that you can create, update and destroy all architecture easily with some commands.

Be aware that you need to be in the Vagrant directory to be able to run the commands.

#### Docker Deployment

You just have to provision the Vagrant instance and the Ansible playbook will automatically be called :

```bash
$ vagrant up
```

If everything run as expected, you should be able to reached the web interface : http://10.0.0.11:8081/

The default login are : admin / password

The default artifactory storage configured is local filestore.

#### Destroy

To destroy the Vagrant resources created, just run this command :

```bash
$ vagrant destroy
```

### How-To

This section list some simple command to use and manage the playbook and the Vagrant hosts.

#### Update with Ansible

To update the artifactory configuration with Ansible, you just have to run the Ansible playbook artifactory.yml with this command :

```bash
$ ansible-playbook artifactory.yml
```

#### Update with Vagrant

To update the artifactory configuration with Vagrant, you just have to run provisioning part of the Vagrant file :

```bash
$ vagrant provision
```

#### Connect to Vagrant instance

To be able to connect to a Vagrant instance, you should use the CLI which is configured to automatically use the default SSH key :

```bash
$ vagrant ssh artifactory01
```

## Author

Member of Wikitops : https://www.wikitops.io/

## Licence

This project is licensed under the Apache License, Version 2.0. For the full text of the license, see the LICENSE file.
