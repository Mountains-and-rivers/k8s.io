# k8s.io kube-apiserver参数解析

### 1，golang 版本

```
go version go1.17.5 windows/amd64 #小于1.17 会报错，有个json 更新
```

### 2，Kubernetes 版本

```
1.22  master
```

### 3, 编译

```
go build -o kube-apiserver.exe
```

### 4, 测试

```
./kube-apiserver.exe --logtostderr=false --v=2 --alsologtostderr=true --etcd-servers=https://192.168.31.240:2379,https://192.168.31.209:2379,https://192.168.31.214:2379 --bind-address=192.168.31.240 --secure-port=6443 --advertise-address=192.168.31.240 --allow-privileged=true --service-cluster-ip-range=10.0.0.0/24 --enable-admission-plugins=NamespaceLifecycle,LimitRanger,ServiceAccount,ResourceQuota,NodeRestriction --authorization-mode=RBAC,Node --enable-bootstrap-token-auth=true --token-auth-file=/opt/kubernetes/cfg/token.csv --service-node-port-range=30000-32767 --kubelet-client-certificate=/opt/kubernetes/ssl/server.pem --kubelet-client-key=/opt/kubernetes/ssl/server-key.pem --tls-cert-file=/opt/kubernetes/ssl/server.pem --tls-private-key-file=/opt/kubernetes/ssl/server-key.pem --client-ca-file=/opt/kubernetes/ssl/ca.pem --service-account-key-file=/opt/kubernetes/ssl/ca-key.pem --etcd-cafile=/opt/etcd/ssl/ca.pem --etcd-certfile=/opt/etcd/ssl/server.pem --etcd-keyfile=/opt/etcd/ssl/server-key.pem --audit-log-maxage=30 --audit-log-maxbackup=3 --audit-log-maxsize=100 --audit-log-path=/opt/kubernetes/logs/k8s-audit.log
```

### 5,结果

![image](https://github.com/Mountains-and-rivers/k8s.io/blob/main/image/1.png)

![image](https://github.com/Mountains-and-rivers/k8s.io/blob/main/image/2.png)



