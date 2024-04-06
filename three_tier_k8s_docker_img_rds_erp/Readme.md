docker images are built from this repository 
````
https://github.com/AnupDudhe/docker-k8s-studentapp-dockerfile-rds-endpoint-
````
kindly refer only 
frontend repo
backend repo

build images on the basis of these two repositort

steps
step1
Dockerfile of frontend backend
push it on dockerhub

step2
create kubernetes manifest file
In
backend repo
deployment.yml and service.yml
mention backendimage name in the deployment

In
frontend repo
deployment.yml and service.yml
mention frontendimage name in the deployment

infra to be created are
#### first and foremost ####
Rds creation
note - the endpoint of the rds will be in your backend repos context.xml

#### second infra to create ####
create a cluster and node 

### third infra to create ###
ec2 instance for building docker images
