Role Name
=========

Lauch AWS instance using Ansible

Requirements
------------

Boto3 library is must to launch instance using ansible but we have already downloaded the same using the role

Role Variables
--------------

You need to create variable file for AWS access and secret key and use the same in playbook while running the playbook
vars_files:
    - password_file



Example Playbook
----------------

- name: launching instances on AWS
  hosts: localhost
  vars_files:
    - keys
  roles:
    - aws_instance

- name: configure webserver
  hosts: webserver
  roles:
    - myapache

- name: configure loadbalancer on lb instance
  hosts: lb
  roles:
     - mylb
