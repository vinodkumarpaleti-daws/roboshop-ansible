## roboshop-ansible

**This repo contains roboshop ansible configuration**

**Dependencies to for ansible to run aws modules**
```agsl
pip3 install botocore boto3
```
```agsl
sudo apt update
sudo dnf install python3-pip -y
pip3 install boto3 botocore
```
**'ec_output.json' file used to read the instance output and create the r53 records**

**command to create the instances and r53 records using ansible (roboshop.yaml) if we are not defining the action by default it will create action**

```agsl
ansible-playbook -i localhost, -e '{"instances":["mongodb","catalogue","redis","user","cart","mysql","shipping","rabbitmq","payment","frontend"]}'  -e action=create roboshop.yaml
```
**command to delete the instances and r53 records using ansible (roboshop.yaml)**
```agsl
ansible-playbook -i localhost, -e '{"instances":["mongodb","catalogue","redis","user","cart","mysql","shipping","rabbitmq","payment","frontend"]}'  -e action=destroy roboshop.yaml
```
## OR

```agsl
ansible-playbook -i localhost, -e "instances=['mongodb','catalogue','redis','user','cart','mysql','shipping','rabbitmq','payment','frontend']" roboshop.yaml
```

***To run the playbook***
```agsl
ex: ansible-playbook -i inventory.ini mongodb.yaml
```

***check the health of the application or server from the Ansible server***
```agsl
ex: curl http://catalogue-dev.jcglobalit.online:8080/health
```