# Prometheus-grafana-alretmanager
# Prometheus-grafana-alretmanager
#!/bin/bash
#需要nfs 目录如下
kubectl create ns monitor-sa
kubectl create serviceaccount monitor -n monitor-sa
kubectl create clusterrolebinding monitor-clusterrolebinding -n monitor-sa --clusterrole=cluster-admin --serviceaccount=monitor-sa:monitor
kubectl -n monitor-sa create secret generic etcd-certs --from-file=/etc/kubernetes/pki/etcd/server.key --from-file=/etc/kubernetes/pki/etcd/server.crt --from-file=/etc/kubernetes/pki/etcd/ca.crt
mkdir -p /data/volumes/prometheus
chmod 777 -R /data/volumes/prometheus
