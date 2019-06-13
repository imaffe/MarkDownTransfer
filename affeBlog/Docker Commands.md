## Docker Commands

docker port CONTAINER : list the port mapping of a container

docker run -d : in detached mode : 

docker log CONTAINER

docker login : 

docker tag IMAGE affe/myimage:tagname

4000:80 80 is the port of container, 4000 is the port of host!

docker container exec -u 0 -it CONTAINER bash

docker run -d -v /var/run/docker.sock:/var/run/docker.sock -v $(which docker):/usr/bin/docker -p 8080:8080 myjenk

```
docker container run --name affe_jenkins_test -p 8002:80 -p 50001:50001  -d jenkins
```

```
docker container run --name myjenkins -p 8003:80 -p 50002:50000 -v $HOME/jenkins2:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock -v $(which docker):/usr/bin/docker -d -it myjenk
```

#### Service

docker-compose.yml



#### Docker Acounts

docker ID : affe

email : affeisme@gmail.com

pass : zhangyufei990513

#### BUGS

why using image :jenkins : no permission

why using image :myjenk : no target file

why using image jenkins : cannot visit the port ? because you need 50000 not 50001

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