Fluntd官網 教學如何收集docker的log
https://docs.fluentd.org/container-deployment/docker-compose

他用了兩種方式來將log傳給EFK
1. 將docker的log轉到 fluent-bit
2. Spring boot 直接轉到flunet-bit
https://ithelp.ithome.com.tw/articles/10266780


# 官網提供的範例無法啟用
https://stackoverflow.com/questions/71120621/efk-system-is-build-on-docker-but-fluentd-cant-start-up