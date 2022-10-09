# ansible-init-ubuntu

A simple interactive script/Ansible playbook that sets up an Ubuntu machine.

As of now it is a very stripped down version of nothebees original ansible vpn script.

## Usage

```
wget https://raw.githubusercontent.com/crabix/ansible-init-ubuntu/main/bootstrap.sh -O bootstrap.sh && bash bootstrap.sh
```

## Features
* SSH hardening
* SSH public key pair generation (optional, you can also use your own keys)
* E-mail notifications (using an external SMTP server e.g. GMail)
* UFW and Fail2Ban

## Requirements
* A KVM-based VPS (or an AWS EC2 instance) with a dedicated IPv4 address
* Ubuntu Server 20.04 or 22.04

## FAQ
### Q: I've run the playbook succesfully, but now I want to change the domain name/username/password. How can I do that?

Edit the variable files, install dependencies for the new user and re-run the playbook:

```
cd $HOME/ansible-init-ubuntu
ansible-galaxy install -r requirements.yml
nano custom.yml
ansible-vault edit secret.yml
ansible-playbook run.yml
```
