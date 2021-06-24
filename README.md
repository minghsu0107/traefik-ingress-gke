# traefik-ingress-gke
This is a demonstration on how to integrate Traefik deployment with ingress provided by GKE.

These files accompany my blog post [All You Need to Know to Integrate Traefik with Cloud Ingress](https://minghsu0107.github.io/posts/integrate-traefik-with-cloud-ingress/).

## Requirements

### GKE version

Your GKE cluster needs to be running at least a recent version 1.17-gke for this to work.

### Static Reserved IP

You need to create a static reserved ip address going by the name of `traefik-ip`.
```bash
gcloud compute addresses create traefik-ip --global
```
### DNS Names
You need to override the domain names of the managed certificate listed in `ingress.yaml`. Make sure they exist and point to `traefik-ip`.
## Installation
```bash
kubectl apply -f manifests/
```
