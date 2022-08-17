# Creating a Dockerfile
1. Specify a base image
2. Run some commands to install additional programs
3. Specify a command to run on container startup

```dockerfile
# 1. base image
# alpine是linux OS
FROM alpine

# 2. Run commands to install additional programs.
# Download and install a Dependency.Running some commands when preparing custom image
RUN apk add --update redis

# 3. Start up command (default command). Conmmand to run on container start up.
# Tell the image what to do when it starts as a container
CMD ["redis-server"]
```

# How to use Dockerfile?

```shell
# using Dockerfile to build image
docker build . 

docker build run {docker id} 

# with tag. the suggestion of name : {dockerid}/projectname
docker build -t {name of image} .
```

# Cache
docker會對intermediate image做快取 (在形成最終image前，那些中間image)，但如果改變Dockerfile，就不會使用Cache。

# Ref.
https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/learn/lecture/11436692#overview