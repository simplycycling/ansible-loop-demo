# ansible-loop-demo
A vagrant-based demonstration of how to pass a loop from a playbook to a role, in Ansible.

## Prerequisites
Ansible and Vagrant

## Usage
### Vagrant
This should work right out of the box, on either Linux or OS X, assuming you have Vagrant installed. You do have Vagrant installed, don't you?
From the command line, run:
vagrant up

### Ansible
This should also work right out of the box, again on Linux and OS X (Windows users, you're on your own). 
There are three playbooks:
- site.yml
- lb.yml
- webserver.yml

Running the 'site.yml' playbook with run both the lb and webserver playbooks:

ansible-playbook site.yml

Or you can run the lb and webserver playbooks individually:

ansible-playbook lb.yml

ansible-playbook webserver.yml

### Troubleshooting
There's not all that much that can go wrong, here, but if you run into an authentication issue with Vagrant, you may need to change the following line in the ansible.cfg file:

private_key_file = ~/.vagrant.d/insecure_private_key

To find out what it should be, run the following command:

vagrant ssh-config

Make note of the location of the insecure_private_key, and replace the file path in the ansible.cfg.
    
