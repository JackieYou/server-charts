# nodeport+external:

```
helm template rancher \
--set hostname=rancher.trinasolar.com \
--namespace cattle-system \
--set service.type=NodePort \
--set service.ports.nodePort=30080 \
--set rancherImage=cnrancher/rancher \
--set rancherImageTag=v2.3.8-ent \
--set auditLog.destination=hostPath \
--set auditLog.hostPath=/var/log/rancher/auditlog/ \
--set auditLog.maxAge=60 \
--set auditLog.maxBackup=100 \
--set auditLog.maxSize=50 \
--set auditLog.level=3 \
--set tls=external \
server-charts/rancher
```

# nodeport+internal+privateca:

```
helm template rancher \
--set hostname=rancher.trinasolar.com \
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

# ingress+internal+privateca:

```
helm template rancher \
--set hostname=rancher.trinasolar.com \
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
