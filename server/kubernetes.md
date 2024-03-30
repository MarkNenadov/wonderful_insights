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
-------------

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
------

Show labels for the deploy:

```
kubectl get deploy my-pod-2 -o jsonpath='{.spec.template.metadata.labels}'
```

List pods for a particular label:

```
kubectl get pods -l app=my-pod-2
```

List pods with their labels printed:

```
kubectl get pods -o custom-columns=NAME:metadata.name,LABELS:metadata.labels
```

Update a label

```
kubectl label pods -l app=my-pod-2 --overwrite app=my-pod-x
```

Get Pod Logs
------------

```
kubectl logs --tail=2 my-pod
```

Get Pod Ip
----------

```
kubectl get pod my-pod -o custom-columns=NAME:metadata.name,POD_IP:status.podIP
```

Get To Shell
------------

```
kubectl exec -it my-pod -- sh
```

Apply a Manifest
----------------

Local file

```
kubectl apply -f my-pod.yaml 
```

Via a Url

```
kubectl apply -f https://my-pod.at.mydomain.com/my-pod.yaml
```

Books
-----

* [Learn Kubernetes in a Month of Lunches](https://www.manning.com/books/learn-kubernetes-in-a-month-of-lunches)
