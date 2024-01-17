# Istio notes
KodeKloud Course

# Resources
Kiali - The Console for Istio Service Mesh
https://kiali.io/

Istio
https://istio.io/latest/docs/setup/getting-started/

## Istio Pre-Requisites
```bash
minikube addons enable ingress
```
output: 
* Verifying ingress addon...
* The 'ingress' addon is enabled

## Istio Installation

```bash
#!/bin/bash
# Download Istio
curl -L https://istio.io/downloadIstio | sh -
export PATH=$PWD/bin:$PATH

# Install Istio
istioctl install --set profile=demo -y

# Verify install Istio
istioctl verify-install
```
# Istio version
```bash
istio version
```
output: 
client version: 1.20.2
control plane version: 1.20.2
data plane version: 1.20.2 (2 proxies)

# Enable istio sidecar Injection
kubectl label namespace default istio-injection=enabled
output: namespace/default labeled
# Install sample app
kubectl apply -f samples/bookinfo/platform/kube/bookinfo.yaml

# check istio-injection
istioctl analyze
output: ✔ No validation issues found when analyzing namespace: default.