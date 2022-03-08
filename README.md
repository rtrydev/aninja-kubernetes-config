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
kubectl create secret generic anime-postgresql --from-literal=POSTGRES_PASSWORD="mysecretpassword"
```

```
kubectl apply -f tags-local-pvc.yaml
kubectl apply -f anime-local-pvc.yaml
kubectl apply -f rabbitmq-depl.yaml
kubectl apply -f tags-postgresql-plat-depl.yaml
kubectl apply -f anime-postgresql-plat-depl.yaml
kubectl apply -f anime-np-srv.yaml
kubectl apply -f anime-depl.yaml
kubectl apply -f tags-depl.yaml
kubectl apply -f ocelot-gateway-depl.yaml
kubectl apply -f ingress-srv.yaml
```
