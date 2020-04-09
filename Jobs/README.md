# Jobs

- A Job creates one or more Pods and ensures that a specified number of them successfully terminate. As pods successfully complete, the Job tracks the successful completions.

- When a specified number of successful completions is reached, the task (ie, Job) is complete. Deleting a Job will clean up the Pods it created.

## Commands

### Create a Job

```console
kubectl create -f [filename] --save-config
```

### Create or Update a Job

```console
kubectl apply -f [filename]
```

### List All Jobs

```console
kubectl get jobs
```

### Delete Job

```console
kubectl delete job [name]
```

# CronJob

- You can use a CronJob to run Jobs on a time-based schedule. These automated jobs run like Cron tasks on a Linux or UNIX system.

## Commands

### Create a CronJob

```console
kubectl create -f [filename] --save-config
```

### Create or Update a CronJob

```console
kubectl apply -f [filename]
```

### List All CronJobs

```console
kubectl get cronCronjobs
```

### Delete CronJob

```console
kubectl delete cronjobs [name]
```
