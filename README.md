# nginx_l7_443(tls)->ingress_80->rancher_80

```
helm install rancher \
--set hostname=<your hostname> \
--namespace cattle-system \
--set rancherImage=cnrancher/rancher \
--set rancherImageTag=v2.3.8-ent \
--set auditLog.destination=hostPath \
--set auditLog.hostPath=/var/log/rancher/auditlog/ \
--set auditLog.maxAge=60 \
--set auditLog.maxBackup=100 \
--set auditLog.maxSize=50 \
--set auditLog.level=3 \
--set tls=external \
--set privateCA=true \
server-charts/rancher
```

# nginx_l7_443(tls)->nodeport_30080->rancher_80

```
helm install rancher \
--set hostname=<your hostname> \
--namespace cattle-system \
--set service.type=NodePort \
--set service.ports.nodePort=300080 \
--set rancherImage=cnrancher/rancher \
--set rancherImageTag=v2.3.8-ent \
--set auditLog.destination=hostPath \
--set auditLog.hostPath=/var/log/rancher/auditlog/ \
--set auditLog.maxAge=60 \
--set auditLog.maxBackup=100 \
--set auditLog.maxSize=50 \
--set auditLog.level=3 \
--set privateCA=true \
--set tls=external \
server-charts/rancher
```

# nginx_l4_443->ingress_443(tls)->rancher_80

```
helm install rancher \
--set hostname=<your hostname> \
--namespace cattle-system \
--set rancherImage=cnrancher/rancher \
--set rancherImageTag=v2.3.8-ent \
--set auditLog.destination=hostPath \
--set auditLog.hostPath=/var/log/rancher/auditlog/ \
--set auditLog.maxAge=60 \
--set auditLog.maxBackup=100 \
--set auditLog.maxSize=50 \
--set auditLog.level=3 \
--set privateCA=true \
server-charts/rancher
```

# nginx_l4_443->nodeport_30443->rancher_443(tls)

```
helm install rancher \
--set hostname=<your hostname> \
--namespace cattle-system \
--set service.type=NodePort \
--set service.ports.nodePort=300443 \
--set rancherImage=cnrancher/rancher \
--set rancherImageTag=v2.3.8-ent \
--set auditLog.destination=hostPath \
--set auditLog.hostPath=/var/log/rancher/auditlog/ \
--set auditLog.maxAge=60 \
--set auditLog.maxBackup=100 \
--set auditLog.maxSize=50 \
--set auditLog.level=3 \
--set privateCA=true \
server-charts/rancher
```
