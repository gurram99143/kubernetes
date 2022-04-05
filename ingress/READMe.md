# ingress

```
In Kubernetes, an Ingress is an object that allows access to your Kubernetes services from outside the Kubernetes cluster.
You configure access by creating a collection of rules that define which inbound connections reach which services.

This lets you consolidate your routing rules into a single resource. For example, you might want to send requests to example.com/api/v1/ to an api-v1 service, and requests to example.com/api/v2/ to the api-v2 service. With an Ingress, you can easily set this up without creating a bunch of LoadBalancers or exposing each service on the Node.
```


## ingress controller
```
In order for the Ingress resource to work, the cluster must have an ingress controller running.

If Kubernetes Ingress is the API object that provides routing rules to manage external access to services, Ingress Controller is the actual implementation of the Ingress API. The Ingress Controller is usually a load balancer for routing external traffic to your Kubernetes cluster and is responsible for L4-L7 Network Services. 

Layer 4 (L4) refers to the connection level of the OSI network stack—external connections load-balanced in a round-robin manner across pods. Layer 7 (L7) refers to the application level of the OSI stack—external connections load-balanced across pods, based on requests. Layer 7 is often preferred, but you should select an Ingress Controller that meets your load balancing and routing requirements.

Ingress Controller is responsible for reading the Ingress Resource information and processing that data accordingly. The following is a sample Ingress Resource:
```

```
apiVersion: networking.k8s.io/v1beta1
kind: Ingress
spec:
  backend:
    serviceName: ServiceName
    servicePort: <Port Number>
```


