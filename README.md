# About this playbook:
This playbook has the objectives to deploy/update via containers the following jfrog components: 
* Artifactory
* XRAYS

The targeted environment are physical/virtual servers. 
JFrog provides already scripts based on docker-compose, HELM. But in case your infrastructure cannot use this nice deployment mechanism or you already based your infrastructure automation strategy on ANsible; These playbooks can be a solution to integrate in you existing ansible ecosystem. 

# Preprequistes:

* Ansible user must be deployed
* Python should be deployed on targeted servers
* SSH pub key should be deployed on all the targeted host:
ssh-keygen -t rsa -C "name@example.org"
ssh-copy-id user@child1.dev


# How to use it:

## Step 1: 

Full filled manually the group_vars --> all.yml within your environment parameter

## Step 2:

From your Host machine launch the playbook deploy.yml.

NB: Several actions need privilege escalation use the following argument inside the playbook call:

''ansible-playbook -i hosts deploy.yml --extra-vars='ansible_become_pass=password' -vvv''
