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

## 補充
### -t and -i
To run an interactive session with a running Docker container we use the docker exec command with the -i and -t flags, or -it for shorter. The -i flag allow us to interact with the container, while the -t flag is used to open a terminal into the container.
The -i flag, or --interactive, instructs Docker to keep STDIN open allowing you to continuously interact with the container.
The -t flag, or --tty, allocates a pseudo-TTY which creates the terminal shell.  
https://stackoverflow.com/questions/22272401/what-does-it-mean-to-attach-a-tty-std-in-out-to-dockers-or-lxc

# Reference
* [Official document](https://docs.docker.com/engine/reference/commandline/cli/)