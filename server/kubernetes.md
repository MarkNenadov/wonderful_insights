Kubernetes insights
===================

Check Your Cluster
-----------------

```kubectl get pods```

Examine a Pod
-------------

```kubectl get pod my-od```

Run a Pod
---------

```
kubectl run my-pod --image=my-pod --restart=Never
kubectl wait --for=condition=Ready pod my-pod
kubectl describe pod my-pod

```
