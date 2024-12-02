Install Python & ansible
$ sudo apt install python3
$ sudo apt install python3-pip
$ sudo apt install ansible
$ pip3 install ansible-lint # linter for ansible

Generate SSH-KEY
$ ssh-keygen -t rsa -b 4096
# exampe path / location ssh-key: ~/.ssh/ansible

Copy *.pub to server
$ ssh-copy-id -f -i <file.pub/location-file.pub> <user>@<ip/domain-host>

SSH login with private key
$ ssh -i <private-key> <user>@<ip/domain-host>

Then check the inventory by displaying all hosts
$ ansible-inventory -i inventory –list

Testing Ansible connection to hosts
$ ansible -i inventory all -m ping

Testing ansible playbooks in several ways
If the error “missing sudo password” add --ask-become-pass or -K
1. $ ansible-playbook -i inventory qemu-agent-playbook.yml
2. $ ansible-playbook qemu-agent-playbook.yml
3. $ ansible-playbook -i inventory qemu-agent-playbook.yml -K
4. $ ansible-playbook qemu-agent-playbook.yml -K

