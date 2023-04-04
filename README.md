# oci-gitops

## bootstrapping the cluster

```
kubectl apply -f https://raw.githubusercontent.com/jpconstantineau/oci-gitops/main/crd/kube-system/calico.yaml

kubectl create namespace argocd 

kubectl apply -n argocd -f https://raw.githubusercontent.com/jpconstantineau/oci-gitops/main/crd/argocd/install.yaml

watch kubectl get pods -A -o wide

kubectl apply -n argocd -f https://raw.githubusercontent.com/jpconstantineau/oci-gitops/main/bootstrap.yaml

kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d > admin-pass.txt

log in and change password.



```


