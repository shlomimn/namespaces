# namespaces

## command set
```
kubectl apply -f namespace.yml
kubectl apply -f nginx_deployment.yml
kubectl apply -f nginx_production.yml
```
<br/>  

## namespaces
```
kubectl get namespaces

NAME                   STATUS   AGE
default                Active   2d11h
development            Active   46m
kube-node-lease        Active   2d11h
kube-public            Active   2d11h
kube-system            Active   2d11h
kubernetes-dashboard   Active   25h
production             Active   46m

```

## development
```
kubectl get all -n development

NAME                         READY   STATUS    RESTARTS   AGE
pod/nginx-55649fd747-tgztg   1/1     Running   0          14m

NAME                    READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/nginx   1/1     1            1           14m

NAME                               DESIRED   CURRENT   READY   AGE
replicaset.apps/nginx-55649fd747   1         1         1       14m

```

## production
```
kubectl get all -n production

NAME                         READY   STATUS    RESTARTS   AGE
pod/nginx-55649fd747-765xm   1/1     Running   0          12m
pod/nginx-55649fd747-jvh46   1/1     Running   0          12m
pod/nginx-55649fd747-xbvw6   1/1     Running   0          12m

NAME                    READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/nginx   3/3     3            3           12m

NAME                               DESIRED   CURRENT   READY   AGE
replicaset.apps/nginx-55649fd747   3         3         3       12m

```
