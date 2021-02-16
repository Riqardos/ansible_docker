# Ansible script for installing Docker on CentOS

### Prerequisities:
- Installed ansible `apt install ansible` (on Ubuntu) for other OSs check [DOCs](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
- Configured ssh connection on local and remote machine
- Create `hosts.yml` file inside this root directory to define remote hosts [DOCs](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html)

### Roles:
- registry - installs Docker and runs Registry container 
- builder - defines Dockerfile, which will be used by building Image and this image will be pushed to already created registry container
- starter - starts container, based on created Image in local registry
- cleaner - reverts all to default state

### Playbooks:
- init_playbook - runs registry, builder and starter roles
- revert_playbook - runs cleaner role

### Config:
- TODO

### Examples: 

To run init_playbook
`ansible-playbook init_playbook.yml -i hosts.yml`

To revert changes
`ansible-playbook revert_playbook.yml -i hosts.yml`


