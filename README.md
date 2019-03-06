# Vagrant Provisioner with Ansible

In this project, Vagrant is provisioned using Ansible to create a working environment I can use for development. The vagrant box is an Ubuntu machine, and the packages are installed using apt-get and pip.

##### Tree Structure
```
.
├── README.md
├── Vagrantfile
├── ansible
│   ├── group_vars
│   │   └── vars.yml
│   ├── inventory.hosts
│   ├── playbook.yml
│   └── tasks
│       ├── apt.yml
│       └── pip.yml
.
```
There are separate playbooks for the apt-get install & pip packages, and these are both imported into the main playbook.yml file.

The terraform version to be downloaded can be specified in the `group_vars/vars.yml` file. For the purposes of my specific workspace, the terraform version is set as 0.10.8.


## How To Run This Project

### Install Vagrant & VirtualBox
Install VirtualBox and Vagrant on your machine.

#### MacOS
Install via brew
```
brew cask install virtualbox
brew cask install vagrant
```

#### Windows

```
```

#### Ubuntu / Debian
```
sudo apt-get install virtualbox
sudo apt-get install vagrant
```

#### CentOS

```
sudo yum install kernel-devel kernel-headers make patch gcc
sudo wget https://download.virtualbox.org/virtualbox/rpm/el/virtualbox.repo -P /etc/yum.repos.d
sudo yum install VirtualBox-5.2
sudo yum install https://releases.hashicorp.com/vagrant/2.2.0/vagrant_2.2.0_x86_64.rpm
```
### Build the Vagrant Box

Once Vagrant and VirtualBox have been installed, clone this project with the following command

`git clone https://github.com/melrobynhogg/vagrant-provisioner.git`


Move into the directory and run the command:

`vagrant up`

This will build the vagrant box and provision it using the ansible script. Once the box has finished building, ssh into the box using the command:

`vagrant ssh`

The Vagrant box is now provisioned and ready to use. To check that it is provisioned correctly, try running the command `aws --version` or `git --version`.
