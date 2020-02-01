# Deployments
- A Deployment provides declarative updates for Pods and ReplicaSets. You describe a desired state in a Deployment, and the Deployment Controller changes the actual state to the desired state at a controlled rate.

#### Create a Deployment:
> `kubectl create -f [filename] --save-config`

#### Create or Update a Deployment:
> `kubectl apply -f [filename]`

#### List All Deployments:
> `kubectl get deployments`

#### List All Deployments with Labels:
> `kubectl get deployments --show-labels`

#### Retrieve Deployments with a Specific Label:
> `kubectl get deployments -l <key>=<value>`

#### Delete Deployment:
> `kubectl delete deployments [name]`

#### Scale Deployment:
> `kubectl scale deployment [name] --replicas=[no-of-replicas]`

#### Scale By Referencing the YAML:
> `kubectl scale -f [name] --replicas=[no-of-replicas]`

#### Scale Deployment:
> `kubectl scale deployment [name] --replicas=[no-of-replicas]`