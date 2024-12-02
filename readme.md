# Install Python & ansible

$ sudo apt install python3

$ sudo apt install python3-pip

$ sudo apt install ansible

## linter for ansible
$ pip3 install ansible-lint 

## Generate SSH-KEY

$ ssh-keygen -t rsa -b 4096

## example path / location ssh-key: ~/.ssh/ansible

## Copy *.pub to server

$ ssh-copy-id -f -i ~/.ssh/ansible.pub srv@10.28.30.11

## SSH login with private key to test

$ ssh -i ~/.ssh/ansible srv@10.28.30.11

## Then check the inventory by displaying all hosts

$ ansible-inventory -i inventory –list

## Testing Ansible connection to hosts

$ ansible -i inventory all -m ping

## Testing ansible playbooks in several ways

## If the error “missing sudo password” add --ask-become-pass or -K

$ ansible-playbook -i inventory qemu-agent-playbook.yml

$ ansible-playbook qemu-agent-playbook.yml

$ ansible-playbook -i inventory qemu-agent-playbook.yml -K

$ ansible-playbook qemu-agent-playbook.yml -K

