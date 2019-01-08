## Docker Commands

docker port CONTAINER : list the port mapping of a container

docker run -d : in detached mode : 

docker login : 

docker tag IMAGE affe/myimage:tagname

docker container ls -a

docker container rm <HASHVALUE>

4000:80 80 is the port of container, 4000 is the port of host!



#### Service

docker-compose.yml

#### Create a docker jenkins

[Jenkins and docker](http://dockone.io/article/2594) , here is where the tutorial come from.

```
sudo docker run -p 8080:8080 -p 50000:50000 -v /var/jenkins:/var/jenkins_home --name my_jenkins -d jenkins
```

- what does -p and the two port mapping means ? 
- what does -v means
- what is the proper permission level of the home dir
- what does the dir mapping do in our docker building ?

check the user permission of current user !

- what does docker run -it means ? 
- why must we use a -v mapping ?  -v means volume, what is a volume in docker ?
  - -v specifies the shared file systems, means --volume
- how to enter a container 
  - docker exec -it <mycontainer> bash

#### Bugs 

- exited with code 1 once created 

#### Docker Acounts

docker ID : affe

email : affeisme@gmail.com

pass : zhangyufei990513

#### Questions

- what is a containers network
- what is virtual ethernet bridge
- what is network virtualization
- what is docker compose
- why using a portnumber/protocol to denote this?
- what is a swarm mode ?
- what is redis
  - an open source , in-memory data structure store
- what is Lua scripting?
- why proxy will block connections to web app once it's up and running?
- what is Flask
- what is curl command ?
- what is a load balance network?
- need something of the networking programming ! 

#### personal info

affe zhangyufei990513

#### Build Failures

- workspace cleanup failed
- pipeline : stage view failed

#### Questions

- what is UUID in most cases !
- what is a bridge in network programming ?
- how to read the documentation notations ? like [host-src: ] container-dest[: <options>]
- what is the difference between bind mount and create a volume for a given name?
  - There is a introduction about volume and bind mounts. You can see from docker documentation.
  - [Storage Management](https://docs.docker.com/storage/)
  - QUES : where is the writable layer in a container ?
  - what is a swarm ? and why is called tmpfs mounts ? 