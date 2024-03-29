Kubernetes
===
node -> deployment -> pod -> container 
---
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
---


Service 設定可以讓指定的容器跟外部進行連線
---
Service 提供述種網路設定

* NodePort 
    
    external network -> (nodePort)node-> cluster(port) -> (targetPort)Pod
    
    注意括弧位置，其位置代表Port的接收/發送方向

* ClusterIP

    cluster -> Pod

    外部無法連上此服務，主要是讓叢集(Cluster)內的Pod與Pod間能夠互相訪問，例如資料庫與網頁

* LoadBalancer
* ExternalName


---



Ingress 類似像apache 的 virtualhost

ConfigMap 扮演不需要加密的字典檔

Secret 與 ConfigMap 正好相反需要對部分設定檔進行加密



* Volumes
    * emptyDir
    * hostPath

PVC(PersistentVolumeClaim) 會找 PV(PersistentVolume) 進行匹配

若無則會以 StorageClass 建立新的"動態匹配"

---
---


minikube
---
minikube start

---

kubeadm
---
kubeadm token create --print-join-command 

更新加入叢集指令


