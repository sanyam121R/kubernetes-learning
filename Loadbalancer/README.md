# Loadbalancing K8s

The Kubernetes load balancer sends connections to the first server in the pool until it is at capacity, and then sends new connections to the next available server. This algorithm is ideal where virtual machines incur a cost, such as in hosted environments.

The load balancer tracks the availability of pods with the Kubernetes Endpoints API. When it receives a request for a specific Kubernetes service, the Kubernetes load balancer sorts in order or round robins the request among relevant Kubernetes pods for the service.
