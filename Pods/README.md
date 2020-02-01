# Pods
- A Pod is the basic execution unit of a Kubernetes application–the smallest and simplest unit in the Kubernetes object model that you create or deploy. A Pod represents processes running on your Cluster.
- A Pod encapsulates an application’s container (or, in some cases, multiple containers), storage resources, a unique network IP, and options that govern how the container(s) should run. A Pod represents a unit of deployment: a single instance of an application in Kubernetes, which might consist of either a single container or a small number of containers that are tightly coupled and that share resources.

> #### Running a Pod
`kubectl run [name] --image=[image-name]`

> #### Create a Pod from YAML
`kubectl create -f [filename] --save-config`

> #### Create or Update a Pod from YAML
`kubectl apply -f [filename]`

> #### Retrieve Pods
`kubectl get pods [name]`

> #### Pod Description
`kubectl describe pod [name]`

> #### Edit Pod
`kubectl edit -f [filename]`

> #### Access Shell of a Pod
`kubectl exec -it [name] sh`

> #### JSON/YAML Formatted Description of a Pod
`kubectl get pod [name] -o [json | yaml]`

> #### Delete a Pod
`kubectl delete pod [name]`
`kubectl delete -f [file]`

### Pod Health
A Probe is a diagnostic performed periodically by the kubelet on a Container.

Each probe has one of three results
1. Success: The Container passed the diagnostic.
2. Failure: The Container failed the diagnostic.
3. Unknown: The diagnostic failed, so no action should be taken.

Types of probes
1. livenessProbe: Indicates whether the Container is running.
2. readinessProbe: Indicates whether the Container is ready to service requests. 
3. startupProbe: Indicates whether the application within the Container is started.
