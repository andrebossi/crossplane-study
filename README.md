# Crossplane Study

- provider.yml - Install Kubernetes provider
- provider-config.yml - provider config for kubernetes
- xrd.yml - Crossplane Resource Definition, schema for create custom Kinds
- xr.yml - Crossplane Resource, Definition for managed resources you use
- xrc.yml - Crossplane ResourceClaim, usage of custom XR

[Docs OpenAPI K8S](https://kubernetes.io/docs/tasks/extend-kubernetes/custom-resources/custom-resource-definitions/)

Install Crossplane
```bash
kubectl create namespace crossplane-system
helm repo add crossplane-stable https://charts.crossplane.io/stable
helm repo update
helm install crossplane --namespace crossplane-system crossplane-stable/crossplane
```
[More install options](https://docs.crossplane.io/v1.10/getting-started/install-configure/)

Install Crossplane Kubectl plugin
```bash
curl -sL https://raw.githubusercontent.com/crossplane/crossplane/master/install.sh | sh
mv kubectl-crossplane /usr/local/bin
```

Run example
```bash
kubectl apply -f provider.yml
kubectl apply -f provider-config.yml
kubectl apply -f xrd.yml
kubectl apply -f xr.yml
kubectl apply -f xrc.yml
```