website
=======

Deployment
----------

### Kubernetes via Helm

Check [values.yaml](./helm/website/values.yaml) for full list of settings:

```bash
cd helm
helm install website \
    # use NodePort for minikube, ClusterIP for ingress-nginx, otherwise LoadBalancer
    --set service.type=NodePort
```

For production use with an existing `ingress-nginx` configuration:

```bash
helm install website \
    --set ingress.enabled=true \
    --set ingress.hosts="{my.host.name,}"
```
