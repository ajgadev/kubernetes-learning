## Kubernetes initial basic YAML File

The YAML file needs 4 basic properties
- apiVersion
- kind
- metadata
- spec

## How to run it
`kubectl create -f pod-definition.yaml`

## How to see it
`kubectl get pods`

`kubectl describe pod myapp-pod`

## How to edit a current pod
`kubectl apply -f pod-definition.yaml`

## How to create an existing image
`kubectl run nginx --image=nginx`

## How to check info about the pod
`kubectl describe pod <pod_id>`

## How delete a POD
`kubectl delete pod <pod_id>`

---
***
___

### Exercise 1
Create a new pod with the name `redis` and the image `redis123`.

### Solution 1
We use `kubectl run` command with `--dry-run=client -o yaml` option to create a manifest file :- <br>
`kubectl run redis --image=redis123 --dry-run=client -o yaml > redis-definition.yaml`


After that, using kubectl create -f command to create a resource from the manifest file :-

`kubectl create -f redis-definition.yaml`
Verify the work by running kubectl get command :-

`kubectl get pods`

### Extra question
Now change the image on this pod to `redis`.

### Solution
Use the `kubectl edit` command to update the image of the pod to `redis`.

`kubectl edit pod redis`

If you used a `pod` definition file then update the image from `redis123` to `redis` in the definition file via Vi or Nano editor and then run `kubectl apply` command to update the image :-

`kubectl apply -f redis-definition.yaml`