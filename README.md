# Kubernetes cluster configuration

## Requirements

* Kubernetes cluster up and running
* kubectl command line installed
* istioctl command line installed
* helm command line installed

## Setup cluster

###### Configure Istio 

```text
istioctl install -f istio-config.yaml
```

###### Configure Istio

```text
istioctl install -f istio-config.yaml
```

###### Declare Istio's gateways

```text
kubectl apply -f gateways.yaml
```

###### Configure management ingress

```text
kubectl apply -f management-ingress.yaml
```

###### Configure API ingress

```text
kubectl apply -f api-ingress.yaml
```

## Setup namespace

###### Create namespace

```text
kubectl create namespace apps
```

###### Set apps namespace as default

```text
kubectl config set-context --current --namespace=apps
```

###### Create environment ConfigMap

```text
kubectl apply -f environment-config.yaml
```

###### Create namespace LimitRange object

```text
kubectl apply -f limit-range.yaml
```

###### Enable Istio's automatic injection

```text
kubectl label namespace default istio-injection=enabled
```

