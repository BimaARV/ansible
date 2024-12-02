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

$ ssh-copy-id -f -i <file.pub/location-file.pub> <user>@<ip/domain-host>

## SSH login with private key

$ ssh -i <private-key> <user>@<ip/domain-host>

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

