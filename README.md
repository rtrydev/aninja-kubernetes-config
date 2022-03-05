# aninja kubernetes setup

## Ingress setup

### Mac

```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.1.1/deploy/static/provider/cloud/deploy.yaml
```

### Linux

```
minikube addons enable ingress
```

## Deploying
```
kubectl create secret generic tags-postgresql --from-literal=POSTGRES_PASSWORD="mysecretpassword"
kubectl create secret generic postgresql --from-literal=POSTGRES_PASSWORD="mysecretpassword"
```

```
kubectl apply -f <file>.yaml
```
