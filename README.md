# Ansible-AMI
This role launches an ec2 instance , configures jenkins , and creates an AMI of the instance.

- Pre-requisites
```
$ sudo apt-get install python-pip
$ sudo pip install ansible==2.7
$ sudo apt-get install ansible -y
$ pip install boto boto3 botocore
$ pip install awscli
$ aws configure
```
- Make sure aws configure is set your aws account , with the correct region.
- AWS ACCESS KEY and SECRET KEY can be generated going to IAM in AWS console.

- In the Ansible.cfg
- Change the private_key_file parameter according to usage
```
[defaults]
host_key_checking = False
remote_user = ubuntu
private_key_file = baston-hashmi.pem
command_warnings = False
deprecation_warnings = False
system_warnings = False
action_warnings = False
```

- In order to run this role , create a playbook which shall call it.
```
---
 - hosts: localhost
   roles:
      - ansible-ami
```
```
$ ansible-playbook ansible-ami.yml
```

