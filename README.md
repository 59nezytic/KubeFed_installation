# KubeFed_installation
Kubefed Installation Scripts

# After Installation
```
$ kubectl config get-contexts
$ vi /root/.kube/config
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
