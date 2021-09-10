A Kubernetes LoadBalancer is a type of Service.
A Kubernetes Ingress is not a type of Service. It is a collection of rules. An Ingress Controller in your cluster watches for Ingress resources, and attempts to update the server side configuration according to the rules specified in the Ingress.
