# Terrafrom with Ansible
I  have written a TerraForm manifest file to create three EC2 instances, by using 'for each block'.

I need to convert one of these instances as a AWS instance. Then this Ansible server is going to manage two different systems and through Ansible playbooks i am going to convert one server as a Jenkins master and another one as a Jenkins slave.

## Features

- Setup 3 EC2 instances through Terraform
- Provision Jenkins-master, Jenkins-slave and Ansible
- Setup Ansible Server
- Configure Jenkins master using Ansible

## Deployment

Instead of running the same script multiple times to create multiple instances rather than this, i am going to use one more parameter called 'for each' to provision different infrastructures.

```bash
  terraform init
```
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/19534cfd-d514-4438-9e9a-b390a5fa4125)

```bash
  terraform validate
```
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/450364b8-d47d-4fac-8cf2-016d95f8c50b)

```bash
  terraform plan
```
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/00d36fa3-83fe-4010-82fb-b0f6efac7c25)
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/889e4641-5492-4eb7-8af2-a252a700be95)

```bash
  terraform apply
```
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/8034008c-d67f-4389-9886-de4e6900ff7c)

**Instance created**
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/28ef9e42-535c-41ab-bfe8-34381cf10c46)

**Login to ansible ec2 instance to setup Ansible**
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/db0d7fe7-9733-4ddb-894b-54351b6f0ecb)

**Check version**
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/55b52b63-8bbe-4489-b1c8-6b56468834ce)

**Now going to add our two systems, that is Jenkins master and slave systems as the managed nodes to Ansible.**
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/2554e4c1-32eb-413c-abb9-b15697f0cb98)

**edit hosts file**

![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/36bb6157-b588-4f9e-be30-d75901032392)

**copy .pem file to /opt location**
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/6397c72f-0961-4d2d-9de2-9061c262577b)

**connecting from ansible to jenkins master**
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/fde62cdc-8c7c-404f-84c3-3ae82c268b8e)

**setup jenkins using Ansible**
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/4c9f6ef9-9fcc-425c-b9c7-d388796801e7)

**Write ansible playbook to install jenkins on Jenkins-master instance**
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/80a14bfd-edfc-40d1-9deb-3a5639b983ea)
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/7384f45f-ca62-4f4c-bc1b-968d42eb5522)

**Run ansible-playbook**
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/f262157d-55e9-4b7c-9fa5-03f3c93d4879)

**Verify java and jenkins installed on jenkins-master instance**
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/2e02fbd5-e8cb-4d1a-819f-693fbf6bdc3d)

**login to jenkins**
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/7e0c7f1c-9625-49f3-8124-a1198ef10f24)
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/2209ce01-cf80-49cb-8c03-fcd31dfc5494)

**Destroy created infrastructure**
![image](https://github.com/Namg04/terraform-with-Ansible/assets/61374484/886943eb-0269-46f2-a22b-f2f2855e60a0)


