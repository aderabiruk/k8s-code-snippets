# Service

- An abstract way to expose an application running on a set of Pods as a network service.
- Kubernetes Pods are mortal. They are born and when they die, they are not resurrected. If you use a DeploymentAn API object that manages a replicated application. to run your app, it can create and destroy Pods dynamically.
- This leads to a problem: if some set of Pods (call them “backends”) provides functionality to other Pods (call them “frontends”) inside your cluster, how do the frontends find out and keep track of which IP address to connect to, so that the frontend can use the backend part of the workload?
- The set of Pods targeted by a Service is usually determined by a selector.

> When a service is created, it's name gets a DNS entry allowing us to access the service using service-name:port.

## Service Types

1. ClusterIP:

- Exposes the Service on a cluster-internal IP.
- This is the default ServiceType.

2. NodePort:

- Exposes the Service on each Node’s IP at a static port (the NodePort).
- A ClusterIP Service, to which the NodePort Service routes, is automatically created.

3. LoadBalancer:

- Exposes the Service externally using a load balancer. 
- NodePort and ClusterIP Services, to which the external load balancer routes, are automatically created.

4. External Names:

- Maps the Service to the contents of the externalName field, by returning a CNAME record

## Commands

### Create a Service

```console
kubectl create -f [filename] --save-config
```

### Create or Update a Service

```console
kubectl apply -f [filename]
```

### Delete a Service using YAML File

```console
kubectl delete -f [filename]
```

### Delete a Service

```console
kubectl delete service [name]
```
