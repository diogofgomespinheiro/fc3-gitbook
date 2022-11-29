# Use kubernetes on your local machine

## Requirements:&#x20;

* [https://kubernetes.io/docs/tasks/tools/install-kubectl-linux](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)
* [https://kind.sigs.k8s.io](https://kind.sigs.k8s.io/)

## Commands:

```bash
kind create cluster OR kind create cluster --name $name
kind create cluster --config $yamlfile
kind get clusters
kind delete cluster OR kind delete clusters $name

kubectl cluster-info --context $name
kubectl config get-clusters
kubectl config use-context $name
kubectl get nodes
```
