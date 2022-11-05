minikube
===
minikube start

node -> deployment -> pod -> container 
===
主要使用 kind:deployment 來進行部屬 pod 

deployment 可以偵測現有的pod群是否有在正常執行，若因pod當中的項目造成當機之類的問題，可以設定至少必須執行的pod數量，deployment會自動刪除當掉的pod 並重新建立新的pod

```
kubectl get pods
kubectl get deployment
kubectl get node
kubectl get service
```

```
kubectl create -f
kubectl create deployment

kubectl 
```

---

Ingress -> Service -> deployment
===


Service 設定可以讓指定的容器跟外部進行連線

Ingress 類似像apache 的 virtualhost



ConfigMap 扮演不需要加密的字典檔

Secret 與 ConfigMap 正好相反需要對部分設定檔進行加密



Volumes

    emptyDir
    hostPath

PVC(PersistentVolumeClaim) 會找 PV(PersistentVolume) 進行匹配

若無則會以 StorageClass 建立新的"動態匹配"