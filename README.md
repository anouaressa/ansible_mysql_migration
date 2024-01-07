The playbook is designed to perform MySQL database-related tasks. In the first play, it creates databases, performs a MySQL dump, and copies the dump file locally. In the second play, it copies the dump file to another server (server2), changes to a specific directory on that server, and imports the database dump into MySQL. The playbook utilizes Ansible modules for MySQL database management.

## you  need to ensure that the MySQL-server is up in the 2 servers
## To install MySQL, run the following command from a terminal prompt:
```
sudo apt install mysql-server´´´
## Once the installation is complete, the MySQL server should be started automatically. You can quickly check its current status via systemd:
```
sudo service mysql status´´´
# you need to have ansible in the one of the servers or an other server ( we have ansible in server1 in our case)

# Installing Ansible
##  include the official project’s PPA
```
sudo apt-add-repository ppa:ansible/ansible´´´
## refresh your system’s package index
```
sudo apt update ´´´
## install the Ansible 
```
sudo apt install ansible´´´

# generate an SSH key on server1 and copy it to server2
## generate an SSH key (by default the ssh key is rsa type if u like to change it use -t and specify the type u like  )
``` 
ssh-keygen ´´´ 
## copying the ssh key from server1 to server2(in our case the the ip address of the server2 is 172.16.2.61 and the user is vagrant)
```
ssh-copy-id user@ip
ssh-copy-id vagrant@172.16.2.61´´´
## the inventory file  defines two groups of hosts, server1 and server2, along with their corresponding connection details.(u need to change it )



