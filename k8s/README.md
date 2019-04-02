## Kube Demo - Basic commands

#### Creating a new deployment
```
kubectl create deployment nginx --image=nginx

kubectl get deployments
```

#### View details of deployment
```
kubectl describe deployment nginx
```

#### Events trigerred in the cluster during the deployment

```
kubectl get events
```

#### Capture output in yaml format
```
kubectl get deployment nginx -o yaml

kubectl get deployment nginx -o yaml > my-nginx.yaml

kubectl get deployment nginx --export -o json

```

#### Delete existing deployment
```
 kubectl delete deployment nginx
 ```

#### Create deployment using file
```
kubectl create -f my-nginx.yaml
```

#### Attaching ports
```
name: nginx
ports:
- containerPort: 80
  protocol: TCP
resources: {}
```

```
kubectl expose deployment/nginx
kubectl get deploy,pod
kubectl get svc nginx
kubectl get ep nginx
 ```


#### Scale the deployment
```
 kubectl scale deployment nginx --replicas=3

 kubectl get deployment nginx
 ```
