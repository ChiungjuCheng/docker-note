# Docker Client
整理一些常用的指令  

## 1. Run command line in docker
```shell
 docker run <image>
 ```
   
  
\<command> 會overwrite原本在image中設定contain要執行的command
 ```shell
 docker run <image> <command>
 ```
例如以下兩個指令，指令2在Conainer被建立出來後就會條列當前目錄，指令1則不做任何事(default設定)
```shell
# 1.
docker run busybox
# 2. 
docker run busybox ls
```

## 2. Retrieving log output
```
docker logs <container-id>
```

## 3. Execute command inside continer
```
docker exec -it <container-id> <command>
```
example:  
```
docker run redis
docker exec -it <redis container id> redis-cli
```

# Reference
* [Official document](https://docs.docker.com/engine/reference/commandline/cli/)