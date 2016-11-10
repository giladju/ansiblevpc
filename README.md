# Ansible Vpc creation 

## General

The purpose of this repo is to demonstrate setting up a vpc in AWS with the following:

* VPC
* Subnets
* Routing tables
* Ops instances (nat and ops)
* Application instances (app, backend)
* Monitoring instance (elk)
* Load balanacers where needed

## Prerequistes

Make sure have set up your user witn AWS CLI key and secret correctly

## Running the playbook

- add an ansible vault password file to your home directory - e.g. ~/.ansible-vault-pw.txt
- run the playbook: 

    cd ansiblevpc
    ansible-playbook vpc-absent.yml -i inventories/poc --vault-password-file=/home/user/.ansible-vault-pw.txt
