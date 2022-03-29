# 建立DockerFile
DockerFile可以在任一路徑底下，但建議可以存放在專案的root路徑。  
DockerFile不用副檔名，只需要將檔案名稱命名為DockerFile (注意大小寫)。  

```
FROM openjdk:11
COPY <src> <dest>
WORKDIR /usr/src
ENTRYPOINT ["java","-jar", "logging-0.0.1-SNAPSHOT.jar"]
```
FROM: 指定要使用的原始映像檔  
COPY: 將檔案複製到指定的容器路徑中
WORKDIR: 設定後續指令(instructions)的工作目錄，後續指令可能為RUN、CMD、ENTRYPOINT等    
ENTRYPOINT:指定容器啟動後執行的命令，每個Dockerfile中只能有一個


# 產生image
在有DockerFile的資料夾下，執行以下指令

```
docker build -t {image-name}
```

# 執行Container
```
 docker run -d -p 8088:8088 {image-name}
```
-d : 在背景執行，避免terminal被鎖定住無法使用  
-p : 設定port，host network : docker network  

# 查看Spring  log

```
 docker logs {{container name}}
```
