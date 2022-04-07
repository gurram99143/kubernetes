```
nfrastructure
Linkerd	Consul	Istio	Kuma	Traefik Mesh	AWS App Mesh
Platforms	Kubernetes	Kubernetes, VM (Universal)	Kubernetes; VM (Universal) is in beta as of 1.9	Kubernetes, VM (Universal)	Kubernetes	AWS EKS, ECS, FARGATE, EC2
High Availability for Control Plane	Yes (creates exactly three control planes)	Yes (with extra servers and agents)	Yes (through Horizontal Pod Autoscaler [HPA] on Kubernetes)	Yes (horizontal scaling)	Yes (horizontal scaling)	Yes (by virtue of supporting AWS tech being HA)
Sidecar Proxy	Yes, linkerd-proxy	Yes, Envoy (can use others)	Yes, Envoy	Yes, Envoy	No	Yes, Envoy
Per-node Agent	No	Yes	No	No	Yes	No
Ingress Controller	Any	Envoy and Ambassador	Istio Ingress or Istio Gateway	Any	Any	AWS Ingress Gateway

```
