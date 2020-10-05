# kubernetes-cheat-sheet


# Basic commands 

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

Secrets:

# Creating a secret without a YAML manifest:
```kubectl create secret generic <name> --from-literal=<key>=<value>```

```kubectl create secret generic <name> --from-file=key=./file.txt```

# Querying secret values via the CLI:

```kubectl get secret <secret-name> -o jsonpath=”{.data.<key-name>}”```

Contexts:

# Get list of contexts

```kubectl config get-contexts```

# Get the current context

```kubectl config current-context <context-name>```

# Switch to current context

```kubectl config use-context <context-name>```


# Logs

# Print the logs for a pod

```kubectl logs <pod_name>```
 

# Print the logs for the last hour for a pod

```kubectl logs --since=1h <pod_name>```
  

# Print the logs for a container in a pod

```kubectl logs -c <container_name> <pod_name>```
 

# View the logs for a previously failed pod

```kubectl logs --previous <pod_name>```
 
 
# Events
 
# List recent events for all resources in the system
 
 ```kubectl get events```
  
 
# List Warnings only
 
 ```kubectl get events --field-selector type=Warning```
  
# List events but exclude Pod events
 
``` kubectl get events --field-selector involvedObject.kind!=Pod```
  
# ReplicaSets

# List ReplicaSets

```kubectl get replicasets```
 
# Display the detailed state of one or more ReplicaSets

```kubectl describe replicasets <replicaset_name>```

# Scale a ReplicaSet

```kubectl scale --replicas=[count] ```
 

#Services

# List one or more services

```kubectl get services```
 

# Display the detailed state of a service

```kubectl describe services```
 

# Expose a replication controller, service, deployment or pod as a new Kubernetes service

```kubectl expose deployment [deployment_name]```
 

# Edit and update the definition of one or more services

```kubectl edit services```
 


 