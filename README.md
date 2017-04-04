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

```
cd ansiblevpc
ansible-playbook vpc-absent.yml -i inventories/poc --vault-password-file=/home/user/.ansible-vault-pw.txt

**Note:** vault password is `V@ult1ng`
```

## Open issues

The following playbooks are not working/tested

* lb
* ops
* abscent

## Manual Clean up 

### EC2

* Enable termination of NAT server
* Terminate all servers
* Load Balancers - delete poc-portal
* Delete `available` volumes

### VPC

* Internet Gateway - detach from vpc
* Internet Gateway - delete
* Subnets - delete subnets `poc_*`
* Route tables - delete route teables `poc*`
* VPC - delete VPC `poc`
