# Volumes

- Docker also has a concept of volumes, though it is somewhat looser and less managed. In Docker, a volume is simply a directory on disk or in another Container. Lifetimes are not managed and until very recently there were only local-disk-backed volumes.

- A Kubernetes volume, on the other hand, has an explicit lifetime - the same as the Pod that encloses it. Consequently, a volume outlives any Containers that run within the Pod, and data is preserved across Container restarts.

- When a Pod ceases to exist, the volume will cease to exist, too. Perhaps more importantly than this, Kubernetes supports many types of volumes, and a Pod can use any number of them simultaneously.

## Types of Volumes

1. emptyDir
: An emptyDir volume is first created when a Pod is assigned to a Node, and exists as long as that Pod is running on that node. As the name says, it is initially empty. Containers in the Pod can all read and write the same files in the emptyDir volume, though that volume can be mounted at the same or different paths in each Container. When a Pod is removed from a node for any reason, the data in the emptyDir is deleted forever.

2. hostPath
: A hostPath volume mounts a file or directory from the host node’s filesystem into your Pod. This is not something that most Pods will need, but it offers a powerful escape hatch for some applications.

3. persistentVolumeClaim
: A persistentVolumeClaim volume is used to mount a PersistentVolume into a Pod. PersistentVolumes are a way for users to “claim” durable storage without knowing the details of the particular cloud environment.

4. Cloud Storage

- AWS
- Azure
- GCP

## StorageClass

- A StorageClass provides a way for administrators to describe the “classes” of storage they offer. Each StorageClass contains the fields provisioner, parameters, and reclaimPolicy, which are used when a PersistentVolume belonging to the class needs to be dynamically provisioned.

## PersistentVolume

- A PersistentVolume (PV) is a piece of storage in the cluster that has been provisioned by an administrator or dynamically provisioned using Storage Classes. It is a resource in the cluster just like a node is a cluster resource. PVs are volume plugins like Volumes, but have a lifecycle independent of any individual Pod that uses the PV.

- A PersistentVolumeClaim (PVC) is a request for storage by a user. It is similar to a Pod. Pods consume node resources and PVCs consume PV resources.

### Reclaiming

- When a user is done with their volume, they can delete the PVC objects from the API that allows reclamation of the resource. The reclaim policy for a PersistentVolume tells the cluster what to do with the volume after it has been released of its claim. Currently, volumes can either be Retained, Recycled, or Deleted.

- [Retain](https://kubernetes.io/docs/concepts/storage/persistent-volumes/#retain)
: The Retain reclaim policy allows for manual reclamation of the resource. When the PersistentVolumeClaim is deleted, the PersistentVolume still exists and the volume is considered “released”. But it is not yet available for another claim because the previous claimant’s data remains on the volume.

- [Delete](https://kubernetes.io/docs/concepts/storage/persistent-volumes/#delete)
: For volume plugins that support the Delete reclaim policy, deletion removes both the PersistentVolume object from Kubernetes, as well as the associated storage asset in the external infrastructure. Volumes that were dynamically provisioned inherit the reclaim policy of their StorageClass, which defaults to Delete.

### Access Modes

1. ReadWriteOnce – the volume can be mounted as read-write by a single node
2. ReadOnlyMany – the volume can be mounted read-only by many nodes
3. ReadWriteMany – the volume can be mounted as read-write by many nodes

### Capacity

- Generally, a PV will have a specific storage capacity. This is set using the PV’s capacity attribute.

### Class

- A PV can have a class, which is specified by setting the storageClassName attribute to the name of a StorageClass. A PV of a particular class can only be bound to PVCs requesting that class. A PV with no storageClassName has no class and can only be bound to PVCs that request no particular class.

### Node Affinity

- A PV can specify node affinity to define constraints that limit what nodes this volume can be accessed from.

## Commands

### Create StorageClass, PersistentVolume or PersistentVolumeClaims

```console
kubectl apply -f [FILE]
```

### Retrieve all StorageClass

```console
kubectl get sc
```

### Retrieve Detail of StorageClass

```console
kubectl get sc -o [yaml | json]
```

### Delete a StorageClass

```console
kubectl delete sc [name]
```

### Retrieve all PersistentVolumes

```console
kubectl get pv
```

### Retrieve Detail of PersistentVolume

```console
kubectl get pv -o [yaml | json]
```

### Delete a PersistentVolume

```console
kubectl delete pv [name]
```

### Retrieve all PersistentVolumeClaims

```console
kubectl get pvc
```

### Retrieve Detail of PersistentVolumeClaim

```console
kubectl get pvc -o [yaml | json]
```

### Delete a PersistentVolumeClaim

```console
kubectl delete pvc [name]
```
