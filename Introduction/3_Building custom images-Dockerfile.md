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
## Basic case
```shell
# using Dockerfile to build image
docker build . 

docker build run {docker id} 

# with tag. the suggestion of name : {dockerid}/projectname
docker build -t {name of image} .
```
## Muti-Step build case
為了讓image變得好維護和降低Image的大小，會將build image拆成幾個階段，某一個階段可能只是為了產生某個資料，拿到資料後就可以刪除該Image了。  
若沒有multi-stage builds就需要寫一個sh來完成整個過程，使得過程變得繁瑣(可參考官網範例)。
### Example:

```Dockerfile
# using AS keyword to name the phase
FROM busybox AS buildFile
RUN touch dummy.txt
RUN echo "dummy">/dummy.txt

FROM busybox
# using --from to refer to the phase
COPY --from=buildFile /dummy.txt ./
CMD ["cat", "./dummy.txt"]
```

[Use multi-stage builds](https://docs.docker.com/develop/develop-images/multistage-build/)

# Cache
docker會對intermediate image做快取 (在形成最終image前，那些中間image)，但如果改變Dockerfile，就不會使用Cache。

# Ref.
* [Dockerfile reference](https://docs.docker.com/engine/reference/builder/)
* https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/learn/lecture/11436692#overview