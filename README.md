# Deployment Instructions
On CLI you can run the command as shown below substituting the user.pem for own aws generated pem and playbook with actual playbook name. Replace the variables in the command to suite your environment.
```
ansible-playbook  -u ec2-user  -i ec2.py  -T 60 -f 100 --private-key=~/user.pem AWSEC2.yml -e "vpc_id={{vpc-id}} zone=a ec2_Name=test ec2_role=test ec2_instance_type='t2.micro' ec2_keypair={{keypair}} ec2_image='{{ami id}}' storage_size=30"
```
You can modify the number hosts and security group by changing the variables:
- ec2_security_group
- ec2_instance_count

## Tower Setup
On Ansible Tower, you will need to let the scm sync and run the project on the UI
P.S.
You might need to define some define some variables to enable for proper deployment of assets and setup

