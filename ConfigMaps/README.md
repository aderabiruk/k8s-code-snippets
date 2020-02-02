# ConfigMap

- ConfigMaps allow you to decouple configuration artifacts from image content to keep containerized applications portable.

## Commands

### Create ConfigMap from a Manifest

```console
kubectl create -f [FILE]
```

### Create ConfigMap from a Key/Value Pair File

```console
kubectl create configmap [NAME] --from-file=[FILE]
```

### Create ConfigMap from an Env File

```console
kubectl create configmap [NAME] --from-env-file=[FILE]
```

### Create ConfigMap from literal values

```console
kubectl create configmap [NAME] --from-literal [KEY]=[VALUE]
```

### Get ConfigMaps

```console
kubectl get cm
```

### Details of a ConfigMap

```console
kubectl get cm [NAME] -o [JSON|YAML]
```