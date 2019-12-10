What was the objective: 

 

Create a High available docker environment 

Nginx as the load balancer  

Appache as the web servers X2 

 

Develop solution on Vagrant ubuntu 16 server 

 

What I did: 

Create Vagrant environment  

Using Vagrant 2.2.2 

Python 3.7.5 

 

Vagrantfile 

Define ubuntu 16 xenial64 

Port forward guest 80 host 8080  

Provision using Ansible  

Use playbook.yml 

 

Ansible 

Install packages and Docker requirements  

Create project directories in usr - [nginx , web1 , web2] 

 

Get nginx files  

Get Dockerfile 

default.conf file 

nginx.conf file 

 

Get Appache files [web1 , web2] 

Dockerfile 

Index.html 

 

Create docker network with custom IPAM 172.20.0.0/16 

Build images from dockerfiles [nginx , web1 , web2] 

 

run the containers  

Start the nginx container on 80:80 ports, connect to docker network and run a HealthCheck (the configuration files are copied via dockerfile COPY command) 

Extended access_log log_format 

 

Start appache containers (index.html is copied via dockerfile COPY command) 

 

 

 

What could I have done better: 

Find a way to pass the node number as a parameter to the index.html 

Find a better way to utilize the nginx default.conf upstream configuration – it is currently a hardcoded IP derived from the docker network ips  



