# Deployments

- A Deployment provides declarative updates for Pods and ReplicaSets.
- You describe a desired state in a Deployment, and the Deployment Controller changes the actual state to the desired state at a controlled rate.
- A ReplicaSet ensures that a specified number of pod replicas are running at any given time. However, a Deployment is a higher-level concept that manages ReplicaSets and provides declarative updates to Pods along with a lot of other useful features.

## Commands

### Create a Deployment

```console
kubectl create -f [filename] --save-config
```

### Create or Update a Deployment

```console
kubectl apply -f [filename]
```

### List All Deployments

```console
kubectl get deployments
```

### List All Deployments with Labels

```console
kubectl get deployments --show-labels
```

### Retrieve Deployments with a Specific Label

```console
kubectl get deployments -l <key>=<value>
```

### Delete Deployment

```console
kubectl delete deployments [name]
```

### Scale Deployment

```console
kubectl scale deployment [name] --replicas=[no-of-replicas]
```

### Scale By Referencing the YAML

```console
kubectl scale -f [name] --replicas=[no-of-replicas]
```

## Rolling Back

### Rollout History

```console
kubectl rollout history deployment [name]
```

### Rollout Status

```console
kubectl rollout status deployment [name]
```

### Rollout History for a Specific Revision

```console
kubectl rollout history deployment [name] --revision=[revision]
```

### Rollback to a Previous Revision

```console
kubectl rollout undo deployment [name] [--revision=[revision]]
```
