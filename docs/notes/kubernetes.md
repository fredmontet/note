Kubernetes
==========

## Run an app from an docker image, image_name can be from a Docker Hub
	
	kubectl run demo --image=<image_name> --port=<port> --labels app=<label>

## Forward a port from the Kubernetes cluster to your machine

	kubectl port-forward deploy/demo 9999:8888

## Check a cluster

	kubectl get pods --selector app=demo

## Get info about all Deployment objects

	kubectl get deployments

## Get info about one Deployment object

	kubectl get deployments <deployment-id> 

## Get in the terminal of a pod

	kubectl exec -it <pod-id> -- bin/bash 
 
## Concepts

In Kubernetes, 3 object types exist:

- Deployment: makes a pod
- Service: connect a pod to a load balanced IP
- Ingress: connect 

## Layer of Abstraction

A Deployment manages a ReplicaSet which manages a Pod that is the abstraction of a container.

## Links

- https://clusterdoc.k8s.tic.heia-fr.ch

