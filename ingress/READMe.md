# ingress

```
In Kubernetes, an Ingress is an object that allows access to your Kubernetes services from outside the Kubernetes cluster.
You configure access by creating a collection of rules that define which inbound connections reach which services.

This lets you consolidate your routing rules into a single resource. For example, you might want to send requests to example.com/api/v1/ to an api-v1 service, and requests to example.com/api/v2/ to the api-v2 service. With an Ingress, you can easily set this up without creating a bunch of LoadBalancers or exposing each service on the Node.
```
