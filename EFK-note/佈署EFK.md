# EFK + Spring boot

兩種方式來將log傳給EFK
#### 1. 將docker的log轉到 fluent-bit 
[Fluntd官網 教學如何收集docker的log](https://docs.fluentd.org/container-deployment/docker-compose)

#### 2. Spring boot 直接轉到flunet-bit  
TODO


目前只實作第一種將docker的log轉到 fluent-bit
# 實作將docker的log轉到fluent-bit
[使用EFK資料夾](/EFK)，建立images和啟動spring boot、fluentd、elasticsearch和kibana容器。  

```
docker-compose up -d
```

## Spring boot
目前spring boot使用[這個專案](https://github.com/ChiungjuCheng/spring-boot-logging)，打http://localhost:8080/api，產生log。
  

## 從kibana查詢log
設定index，讀取特定的資料來源。 index可以從以下網頁設定:  
http://localhost:5601/app/management/kibana/indexPatterns

# 官網提供的範例無法啟用
可能是因為版本問題，調整版本後就可以啟動了  
https://stackoverflow.com/questions/71120621/efk-system-is-build-on-docker-but-fluentd-cant-start-up