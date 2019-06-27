Preprequistes:

* Ansible user must be deployed
* Python should be deployed on targeted servers
* SSH pub key should be deployed on all the targeted host:
ssh-keygen -t rsa -C "name@example.org"
ssh-copy-id user@child1.dev


How to use it:
From your Host machine launch the playbook deploy.yml.

NB: Several actions need privilege escalation use the following argument inside the playbook call:

ansible-playbook -i hosts deploy.yml --extra-vars='ansible_become_pass=password' -vvv
