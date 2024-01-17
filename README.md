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