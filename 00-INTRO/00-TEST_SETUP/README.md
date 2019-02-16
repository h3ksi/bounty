# This document describes steps I went through to deploy my first app on Kubernetes cluster on k8.si

## Step1: Get your config.yaml and set up kubectl

Visit https://login.k8.si

Download config.yaml

** if you do not have allready install kubeclt https://kubernetes.io/docs/tasks/tools/install-kubectl/  **

Save config.yaml as `~/.kube/config-hek`

You can see config used by kubernetes with

 `kubectl config view`

To se hekovnik config use

 `kubectl --kubeconfig config-hek config view`

 so to use config for hekovnik you need to use `--kubeconfig config-hek` flag.

## Step2: deploy demo app to test if it work

use copy `00-demo.yaml`

edit all instances of `whoami.k8.si` with your team name `teamname.whoami.k8.si`
You can also update certificate secretName

`kubectl create --kubeconfig ~/.kube/config-hek -f 00-demo.yaml`

check if it works you expect response like this:
```
deployment.apps "whoami" created
service "whoami" created
ingress.extensions "whoami" created
```

and you should be able to visit https://<teamname>.whoami.k8.si

## Step3: clean up 

You cen stop this application and clean up pods.

use `kubectl delete --kubeconfig ~/.kube/config-hek -f 00-demo.yaml`


**So now you know how to deploy and remove application from kubernetes!**