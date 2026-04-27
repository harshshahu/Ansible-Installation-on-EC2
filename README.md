# Ansible-Installation-on-EC2
1. Create 3 EC2 instances:
  1. EC2 name: Ansible-Server
     EC2 type: t2-medium.
  2. EC2 name: Host-1
     EC2 type: t3-micro.
  3. EC2 name: Host-2
     EC2 type: t3-micro.

2. Connect to Ansible-Server EC2 instance, and execute all the below commands:
   sudo dnf update -y
   sudo dnf install python pip tree git -y
   sudo pip install ansible.noarch -y
   cd etc/ansible/
3. Execute/type below commands:
   sudo touch ansible.cfg
   sudo mkdir inventory
   cd inventory/
   sudo touch hosts
   cd ..
   sudo mkdir aws
   cd aws/
   sudo nano ansible.pem
   (Open your .pem file(key-pair) from your local machine location: study:D/DevOps/KeyPair/DevOps.pem)
   copy all the content and paste it on 'ansible.pem'.
   save & exit

4. Execute/type below commands:
   cd ..
   sudo mkdir playbooks
   cd playbooks/
   sudo touch ping.yml
   cd ..
   tree
   you will see below tree:
   |
   |--ansible.cfg
   |
   |--aws
   |   |--ansible.pem
   |
   |--inventory
   |   |--hosts
   |
   |--playbooks
   |    |--ping.yml
   |
   |--roles


5. Execute/type below commands:
   cd inventory/
   sudo nano hosts
     type below:
       [all]
       public-ip (of your Host-1 EC2)
       public-ip (of your Host-2 EC2)
   save & exit

6. Execute/type below commands:
   sudo nano ansible.cfg
   (Open Github repository: )
