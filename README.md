# KubeFed_installation
Kubefed Installation Scripts

# After Installation
```
$ kubectl config get-contexts
$ vi /root/.kube/config
```
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
(join은 host cluster에서 원하는 cluster join 하는 형식 !)![image](https://user-images.githubusercontent.com/55429907/150331751-fa38ce7f-fdca-401e-b96b-46b8d1807f92.png)
```
