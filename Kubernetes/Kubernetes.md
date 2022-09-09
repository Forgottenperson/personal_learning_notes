# minikube
```
minikube start
```
# container -> pod -> deployment -> node
# 主要使用 kind:deployment 來進行部屬 pod 
# deployment 可以偵測現有的pod群是否有在正常執行，若因pod當中的項目造成當機之類的問題，可以設定至少必須執行的pod數量，deployment會自動刪除當掉的pod 並重新建立新的pod
```
kubectl get pods
kubectl get deployment
kubectl get node
kubectl get service
```

kubectl create -f
kubectl create deployment

kubectl 