# Secrets

- Kubernetes secret objects let you store and manage sensitive information


## Commands

### Create a Secret from File

```console
kubectl create secret generic [NAME] --from-file=[FILE]
```

### Create a Secret from ENV File

```console
kubectl create secret generic [NAME] --from-env-file=[FILE]
```

### Create a Secret from a Literal Value

```console
kubectl create secret generic [NAME] --from-literal [KEY]=[VALUE]
```

### Get Secrets

```console
kubectl get secrets
```

### Get a Description of a Secret

```console
kubectl get secrets [NAME] -o [JSOM|YAML]
```
