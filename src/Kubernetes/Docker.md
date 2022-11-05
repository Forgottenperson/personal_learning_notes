執行起一個容器
```
docker run -it -p 5000:6000 "container-image" bash
```

-it : 以tty介面對容器逕行訪問
-p : 將Host port 對應到 container 的 port

bash : 以 /bin/bash 的 shell介面進行訪問 也有 /bin/sh 可選


登入容器內的tty介面
```
docker exec -it "container-id" bash
```

容器的啟動關閉與重啟
```
docker start "container-id"
docker stop "container-id"
docker restart "container-id"
```

將容器狀態儲存成新的image檔
```
docker commit -m "message" "container-id" "new-container-image"
```

將容器的image檔 另存/讀取 成一個檔案
```
docker save -o image.tar "container-image" 
docker load --input image.tar "container-image" 
```

移除執行中的容器
```
docker rm "container-id"
```
移除現有的容器image檔
```
docker rmi "container-image"
```

其他 

registry image 

建立私有的container儲存庫