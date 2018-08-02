# k8s.gcr.io

## 安装 kubeadm

## 系统环境
 
> setenforce 0


## aliyun + github 构建私有 docker 镜像

## 拉取镜像
- ```docker pull registry.cn-hangzhou.aliyuncs.com/nickel/kube-apiserver-amd64:v1.11.1```



## docker 镜像列表

- k8s.gcr.io/kube-apiserver-amd64:v1.11.1
- k8s.gcr.io/kube-controller-manager-amd64:v1.11.1
- k8s.gcr.io/kube-scheduler-amd64:v1.11.1
- k8s.gcr.io/kube-proxy-amd64:v1.11.1
- k8s.gcr.io/pause:3.1
- k8s.gcr.io/etcd-amd64:3.2.18
- k8s.gcr.io/coredns:1.1.3


## 重命名镜像
- ```docker tag registry.cn-hangzhou.aliyuncs.com/nickel/kube-apiserver-amd64:v1.11.1 k8s.gcr.io/kube-apiserver-amd64:v1.11.1```
- ```docker tag registry.cn-hangzhou.aliyuncs.com/nickel/kube-controller-manager-amd64:v1.11.1 k8s.gcr.io/kube-controller-manager-amd64:v1.11.1```
- ```docker tag registry.cn-hangzhou.aliyuncs.com/nickel/kube-scheduler-amd64:v1.11.1 k8s.gcr.io/kube-scheduler-amd64:v1.11.1```
- ```docker tag registry.cn-hangzhou.aliyuncs.com/nickel/kube-proxy-amd64:v1.11.1 k8s.gcr.io/kube-proxy-amd64:v1.11.1```
- ```docker tag registry.cn-hangzhou.aliyuncs.com/nickel/pause:3.1 k8s.gcr.io/pause:3.1```
- ```docker tag registry.cn-hangzhou.aliyuncs.com/nickel/etcd-amd64:3.2.18 k8s.gcr.io/etcd-amd64:3.2.18```
- ```docker tag registry.cn-hangzhou.aliyuncs.com/nickel/coredns:1.1.3 k8s.gcr.io/coredns:1.1.3```

## 初始化

> kubeadm init --kubernetes-version=1.11.1 --apiserver-advertise-address=192.168.83.134 --pod-network-cidr=10.244.0.0/16 

## 重置初始化
> kubeadm reset


## 删除 dashbord
> kubectl -n kube-system delete $(kubectl -n kube-system get pod -o name | grep dashboard)
## proxy 
kubectl proxy --address='0.0.0.0'  --accept-hosts='^*$'

