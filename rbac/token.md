### Jenkins token required to authenticate against the Kubernetes cluster
Generate a Kubernetes ServiceAccount token for Jenkins (valid for 24 hours):
```sh
kubectl create token jenkins -n dev --duration=24h
```
**Note:** Create ServiceAccount first
