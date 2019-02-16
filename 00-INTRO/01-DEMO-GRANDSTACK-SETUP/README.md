# GRANDstack Starter on Kubernetes
This how2 shows how to prepare kubernets yaml files and deploy [GRANDstack starter](https://github.com/grand-stack/grand-stack-starter) app to kubernetes cluster.

## Quickstart
1. Clone [GRANDstack starter](https://github.com/grand-stack/grand-stack-starter) to your local environment
2. Prepre `.env` files for each part of app so that they suit your needs
3. Build docker images for each part of the app: database, ui, app
4. Push docker images to your dockerhub account
5. Install kubectl on local machine (if not already)
6. Download k8.si token 
7. edit kubernetes-demo.yaml and fill-data.yaml to reflect your settings
   1. Database ip,
   2. Domain (from hekovnik.dockerstack.k8.si to <yourteam>.dockerstack.k8.si)
   3. Docker hub docker image
8. Create app with `kubectl --kubeconfig ~/.kube/config-hek create -f kubernetes-demo.yaml`
9.  Fill app with `kubect--kubeconfig ~/.kube/config-hek create -f fill-data.yaml`
10. You can access database interface with `kubectl --kubeconfig ~/.kube/config-hek port-forward neo4j-0 7374 7587`

