# Docker
TODO  
overview
# Docker object
使用docker時，會創建或使用images, containers, networks, volumes, plugins, 和其他object，以下做簡短的介紹

## Images
* images以唯獨的方式建立容器運行的基礎環境，其包含應用程式和相關依賴庫的檔案

## Containers
* Container是在image的基礎上建立的執行狀態
* 在default設定中，container之間是相互隔離的
* 除了使用image定義container外，使用者在創建和啟動container時，也能夠提供configuration options來定義container。