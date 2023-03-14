# multi-lobby-message-service

Multi Lobby Message Service (MLMS) is a Shared-Nothing distributed computing solution to handling many concurrent connections and messages.

## Core Structure 

Highly subject to change and this will be updated as the project progresses.

1. Load balancer / connection broker to route incoming traffic.
2. On a valid connection, the user will be routed to a lobby.
    2a. If the lobby doesn't exist, a lobby will be created.
3. Redis will be used as a cache layer or message broker between different parts of the application.
4. Database will likely be MySQL.

Each element of the application will be containerised and managed through Docker. As the application grows, it may be required to use Kubernetes OR an AWS ECS.

![DS Diagram](https://i.imgur.com/unhMuGq.png)

## Milestones

0. Init project with both AWS and Minikube kubernetes. ✅

1. Setup ingress controller to route traffic to 'Hello World' page on request. ✅

2. Create a service will take the route from an ingress controller and create a new instance of a container. i.e. Hello World 

3. Pass in lobby arguments to the new container.


## Learnings

## 14/03/2023

Kubernetes single node local configurations have been a bit frustrating to to get going. The experience of updating deployments
on `eksctl` has been smoother than via Minikube.

The main problem that I ran into was wanting to access the pod directly to test the ingress controller. i.e. pod-url/hello. However,
this isn't the case from what I've found out of the box. The single node cluster doesn't appear to have any external IPs setup so for now
it makes more sense for me to run:

```sh
kubectl port-forward <pod-name> 8080:80
```

After we've done that, our test ingress controller routes invalid routes to a /404 and our valid route to a 'Hello World' page.

Next step is going to be

## 13/03/2023

Deployed a simple nginx container on AWS EKS, Minikube and set up dashboards on both.
Development will be carried out on a single node in Minikube and ported to AWS at the end of each milestone for testing.


