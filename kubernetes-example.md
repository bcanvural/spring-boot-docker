## Start minikube
```bash
$ minikube start
```
## Get Nodes
```bash
$ kubectl get nodes
```

## Create a deployment
```bash
$ kubectl run mydeployment --image=docker.io/bcanvural/gs-spring-boot-docker --port 8080
```
## See deployments
```bash
$ kubectl get deployments
```
## Get pods
```bash
$ kubectl get pods
```
## Set pod name
```bash
$ export POD_NAME=podname_from_above_command
```
## Describe a pod
```bash
$ kubectl describe $POD_NAME
```
## Start interactive bash session with the container in pod

```bash
$ kubectl exec -it $POD_NAME --container mydeployment  bash
```

## Start proxy

```bash
$ kubectl proxy
```

## Call the app using proxy

```bash
$ curl http://localhost:8001/api/v1/proxy/namespaces/default/pods/$POD_NAME/
```
## Expose the app

```bash
$ kubectl expose deployment/mydeployment --type="NodePort" --port 8080
```

## Find Node IP and Node Port
Find node ip in:
```bash
$ kubectl describe node minikube
```
Find node port in:

```bash
$ kubectl describe service mydeployment
```

## Access exposed app from outside

```bash
$ curl http://$NODE_IP:$NODE_PORT
```

