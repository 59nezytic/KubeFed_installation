# KubeFed_installation
Kubefed Installation Scripts

# After Installation
```
$ kubectl config get-contexts
$ vi /root/.kube/config
```
# kube_config example
```
host cluster = cluster1
member cluster = cluster2
############################################################
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: REDACTED
    server: https://192.168.10.146:6443
  name: host-cluster
- cluster:
    certificate-authority-data: REDACTED
    server: https://192.168.10.17:6443
  name: member-cluster

contexts:
- context:
    cluster: host-cluster
    user: host-cluster-admin
  name: cluster1
- context:
    cluster: member-cluster
    user: member-cluster-admin
  name: cluster2

current-context: cluster1

kind: Config
preferences: {}

users:
- name: host-cluster-admin
  user:
    client-certificate-data: REDACTED
    client-key-data: REDACTED
- name: member-cluster-admin
  user:
    client-certificate-data: REDACTED
    client-key-data: REDACTED
```

# After Change Your own kube_config
```
$  systemctl daemon-reload
$  systemctl restart kubelet
```
```
$ kubectl config view
$ kubectl config use-context {CONTEXT_NAME}
```
```
$ kubefedctl join {CONTEXT_NAME} --cluster-context {CONTEXT_NAME} --host-cluster-context {HOSTCLUSTER_CONTEXT_NAME} --kubefed-namespace=kube-federation-system --v=2
(Member cluster joining to Host cluster)
```
