Fluntd官網 教學如何收集docker的log
https://docs.fluentd.org/container-deployment/docker-compose

兩種方式來將log傳給EFK
1. 將docker的log轉到 fluent-bit
2. Spring boot 直接轉到flunet-bit

# 實作
使用EFK資料夾
```
docker-compose up -d
```

到這個網頁建立index
http://localhost:5601/app/management/kibana/indexPatterns

# 連接spring boot
目前spring boot

# 官網提供的範例無法啟用
https://stackoverflow.com/questions/71120621/efk-system-is-build-on-docker-but-fluentd-cant-start-up