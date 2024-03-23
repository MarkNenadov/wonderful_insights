Kubernetes insights
===================

Check Your Cluster
-----------------

```kubectl get notes```

Run a Pod
---------

```
kubectl run my-pod --image=my-pod --restart=Never
kubectl wait --for=condition=Ready pod my-pod
kubectl describe pod my-pod

```
