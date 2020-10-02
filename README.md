# kubernetes-cheat-sheet


# To find kubectl version
```kubectl version```

# To list kubectl cluster information 
```kubectl cluster-info```

# To view nodes in the cluster
``` kubectl get nodes```

# To run app with kubernetes
```kubectl run <appname> --image=<imagelocation> --p <portno>```

# To list deployments
``` kubectl get deployments```

# To list pods
```kubectl get pods```

# To view containers and their details in the pod
 ```kubectl describe pods```

# To list services
```kubectl get services```

# To expose a service
```kubectl expose```

# To view the label
```kubectl describe deployment```

# To delete the service
```kubectl delete service```

Deployments

# Deployment without YAML manifest: 
``` kubectl create deployment <name> --image= <image> ```
# Scale deployments:
 ``` kubectl scale deployment <deployment> --replicas=<number> ```
# Rollout status: 
``` kubectl rollout status deployment <deployment> ```
# Rollout re-start:
 ``` kubectl rollout restart deployment <deployment> ```
# Rollout history: 
``` kubectl rollout history deployment <deployment> ```
# Undo rollout: 
``` kubectl rollout undo deploy <deployment> --to revision= <revision> ```

Services 

# Creating a service without a YAML manifest:
```kubectl expose pod/deployment <name> --port x --target-port x```

# Showing labels:
```kubectl get services --show-labels```

Pods:

# To execute command on pod 
```kubectl exec -ti $POD_NAME curl www.google.com```
# Provision a pod:
```kubectl run <pod-name> --image=<image-name>--restart=Never ```
# Commands to a running container:
```kubectl exec -ti <pod-name> <command>```
# Specify a container: 
```kubectl exec -ti <pod-name> -c <container> sh ```

