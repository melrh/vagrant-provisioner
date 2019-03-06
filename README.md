Vagrant Provisioner with Ansible

Vagrant is provisioned using Ansible to create a working environment. The vagrant box is an Ubuntu machine, and the packages are installed using apt-get and pip.

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
└── ansible.cfg

There are separate playbooks for the apt-get install & pip packages, and these are both imported into the main playbook.yml file.

The terraform version to be downloaded can be specified in the group_vars/vars.yml file. For the purposes of my specific workspace, the terraform version is set as 0.10.8.
