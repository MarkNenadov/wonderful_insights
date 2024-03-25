Kubernetes insights
===================

Check Your Cluster
-----------------

```kubectl get pods```

Examine a Pod
-------------

```kubectl get pod my-pod```

Note: To get more details, you can pass --output custom-columns=xyz, for instance:

```
kubectl get pod my-pod --output custom-columns=NODE_IP:status.hostIP,POD_IP:status.podIP
```

You can also specify custom columns via a JSONPath

```
kubectl get pod hello-kiamol -o jsonpath='{.status.containerStatuses[0].containerID}'
```

Run a Pod
---------

```
kubectl run my-pod --image=my-pod --restart=Never
kubectl wait --for=condition=Ready pod my-pod
kubectl describe pod my-pod

```

Redirect Port
=============

Listen to port 9090 on local machine and forward it to 80 within the pod:

```
kubectl port-forward pod/my-pod 9090:80
```

Create Deployment
-----------------

```
kubectl create deployment my-pod-2 --image=my-pod
```

Labels
======

Show labels for the deploy:

```
kubectl get deploy my-pod-2 -o jsonpath='{.spec.template.metadata.labels}'
```

List pods by label:

```
kubectl get pods -l app=my-pod-2
```
Books
=====

* [Learn Kubernetes in a Month of Lunches](https://www.manning.com/books/learn-kubernetes-in-a-month-of-lunches)
