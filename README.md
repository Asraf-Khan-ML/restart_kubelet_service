##Ansible script to restart k8's node kubelet service

ansible.cfg - Ansible configuration file.

hosts - Ansible Inventory File

playbooks - Its a directory holds all playbooks.

Requirement: 

	1. install ansible 

    Centos:
        yum install epel-release -y
        yum install ansible

    Ubuntu: 
        Log into the Ubuntu Server that will host Ansible
        Install the necessary repository with the command sudo apt-add-repository ppa:ansible/ansible.
        Update apt with the command sudo apt-get update.
        Install Ansible with the command sudo apt-get install ansible -y.
 
    2. copy node ssh key to local machine and change permission with chmod 400  <ssh key>
	
	3. Update nodes details in host file.

Execution:

	ansible-playbook restart_kubelet.yml --key-file=<path to ssh key file>  -b -v

	Example
		ansible-playbook restart_kubelet.yml --key-file=/home/centos/user-qa-aws-ssh.pem -b -v
