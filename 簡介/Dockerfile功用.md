# Creating a Dockerfile
1. Specify a base image
2. Run some commands to install additional programs
3. Specify a command to run on container startup

```dockerfile
# base image
FROM alpine
# Download and install a Dependency.Running some commands when preparing custom image
RUN apk add --update redis
# Tell the image what to do when it starts as a container
CMD ["redis-server"]
```
**Base image**  
alpine是linux OS

**RUN**  
在建立image時期，告訴alpine做甚麼

**CMD**  
使用該image啟動時要執行的命令


## 來源
https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/learn/lecture/11436692#overview