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

Deployments
-----------

Create

```
kubectl create deployment my-pod-2 --image=my-pod
```

Delete All Deployments

```
kubectl delete deploy --all
````

ReplicaSets
-----------

Show
```
kubectl get rs my-replicaset
kubectl get replicaset my-replicaset

```

Show Labels
```
kubectl get rs -l app=pi-web --show-labels
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

Environment Variables
---------------------

Print an Environment Varible

```
kubectl exec my-pod -- printenv HOSTNAME
```

Set An Environment Variable. In your yaml file, under containers put:
```
env:
- name: BASE_URL
  value: "http://localhost:8080/web/"
```

ConfigMaps
----------

Create a ConfigMap
```
kubectl create configmap my-app-config --from-literal=my-app.baseUrl='http://localhost:8080/web'
```

Output a ConfigMap value / Describe It
```
kubectl get cm my-app-config
kubectl describe cm my-app-config
```


Set An Environment Variable from a ConfigMap:
```
env:
- name: BASE_URL
  valueFrom:
    configMapKeyRef:
        name: my-app-config
        key: my-app.baseUrl
```

Load an environment file into a ConfigMap:

```
kubectl create configmap my-env-map --from-env-file=my.env
```


Run Shell Command
-----------------

```
kubectl exec my-pod -- ls
```

Get To Shell
------------

```
kubectl exec -it my-pod -- sh
```

Copy Files
----------

```
kubectl cp my-pod:/src/folder/on/pod /file/on/my/filesystem
```

Delete Pods
---------------

Delete a Pod

```
kubectl delete pod -l app=my-pod
```

Delete All Pods
Note: This will not remove podst which were created by Deployments.

```
kubectl delete pods --all
```

Delete Resources In A Diretory
------------------------------

```
kubectl delete -f my-dir/
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

Imperatively Scale a Controller
-------------------------------

kubectl scale --replicas=10 my-app

Services
--------

List All Services

```
kubectl get svc
```


List All Services In A Namespace

```
kubectl get svc --namespace default
kubectl get svc --namespace kube-system
```

Get Info About a Service

```
kubectl get svc my-service
```

Delete a Service


```
kubectl delete svc my-service
```

Delete All Serivces

```
kubectl delete svc --all
```

Get Info About Endpoints
------------------------

List All
```
hubectl get endpoints
```

Single endpoint

```
kubectl get endpoints my-endpoint
```

Secrets
-------

Create a secret

```
kubectl create secret generic my-secret-literal --from-literal=key=value
```

Describe a secret

```
kubectl describe secret my-secret-literal
```

Retreive a secret value
```
kubectl get secret my-secret-literal -o jsonpath='{.data.key}'|base64 -d
```

Books
-----

* [Learn Kubernetes in a Month of Lunches](https://www.manning.com/books/learn-kubernetes-in-a-month-of-lunches)
