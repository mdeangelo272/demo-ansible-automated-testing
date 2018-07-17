# Ansible Automated Testing Demo
This is a sample project to demonstrate different technologies and best practices relating to automating testing in Ansible. The playbook will install a [gogs](https://gogs.io/) Git Server using existing Ansible Roles in Ansible Galaxy.

The presentation can be seen on [GitPitch](https://gitpitch.com/mdeangelo272/ansible-automated-testing-demo/meetup_dallas).

## Usage

### Requirements
* Python (developed using 3.6.1)
* pip (developed using 10.0.1)
* Ansible (developed using 2.6.1)
* VirtualBox (developed using 5.2.12)
* Vagrant (developed using 2.1.1)

### Provisioning the VM
Install galaxy dependencies:
```
ansible-galaxy install -r requirements.yml
```

Create the VM and provision it using Vagrant:
```
vagrant up
```

This creates a new VM and installs Gogs using Ansible. You can see the gogs server at http://127.0.0.1:3000

The database user and password are both `gogs_db`. You can create a user account on the [sign up page](http://localhost:3000/user/sign_up).

### Solution Overview
The `Vagrantfile` defines the configuration for the VM. 

The `requirements.yml` define the requirements for the playbooks that are available in galaxy. 

The `main.yml` playbook install `gogs` and `mysql` on the Vagrant VM. 

The `tests` directory contains the automated tests implemented using Ansible tasks. In the future, I would like to add example automated tests using other frameworks and technologies. 

