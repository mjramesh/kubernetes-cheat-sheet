# kubernetes-cheat-sheet
kubernetes commands for easy reference

# To find kubectl version

```
 kubectl version
```

# To list kubectl cluster information

```
 kubectl cluster-info
```

# To view nodes in the cluster

```
 kubectl get nodes
```

# To run app with kubernetes

```
 kubectl run <appname> --image=<imagelocation> --p <portno>
```

# To list deployments

```
 kubectl get deployments
```

# To list pods

```
 kubectl get pods
```

# To view containers and their details in the pod 

```
 kubectl describe pods
```

# To list services

```
 kubectl get services
```

# To expose a service

```
 kubectl expose
```

# To view the label
```
kubectl describe deployment
```

# To delete the service
```
kubectl delete service
```

# To execute command on pod

```
kubectl exec -ti $POD_NAME curl www.google.com
```

# To scale the deployments

```
kubectl scale <deploymentname> --replicas=<count>
```