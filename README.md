# kube-httpcache-chart
Inspired by https://github.com/mittwald/kube-httpcache. helm chart for kube-httpcache with scalable frontend 


run following before install
```
$ kubectl create secret generic varnish-secret --from-literal=secret=$(head -c32 /dev/urandom  | base64)
```

if RBAC is enabled you may need to run these too.
```
$ kubectl create serviceaccount kube-httpcache
$ kubectl apply -f https://raw.githubusercontent.com/mittwald/kube-httpcache/master/deploy/rbac.yaml
$ kubectl create rolebinding kube-httpcache --role=kube-httpcache --serviceaccount=kube-httpcache
```
