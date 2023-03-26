# Prometheus-grafana-alretmanager
# Prometheus-grafana-alretmanager
<br>#!/bin/bash
<br>#需要nfs 目录如下
<br>kubectl create ns monitor-sa
<br>kubectl create serviceaccount monitor -n monitor-sa
<br>kubectl create clusterrolebinding monitor-clusterrolebinding -n monitor-sa --clusterrole=cluster-admin --serviceaccount=monitor-sa:monitor
<br>kubectl -n monitor-sa create secret generic etcd-certs --from-file=/etc/kubernetes/pki/etcd/server.key --from-file=/etc/kubernetes/pki/etcd/server.crt --from-file=/etc/kubernetes/pki/etcd/ca.crt
<br>mkdir -p /data/volumes/prometheus
<br>chmod 777 -R /data/volumes/prometheus
