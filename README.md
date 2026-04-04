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