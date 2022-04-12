# my-k8s

try and test my own k8s stuff

### start kubernetes from docker

    ➜  ~ kubectl get node
    NAME             STATUS   ROLES                  AGE    VERSION
    docker-desktop   Ready    control-plane,master   2m1s   v1.22.5

### install helm

    brew install helm

### deploy the nginx ingress controller

    helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx

The above line adds helm repo, we can check it via `helm repo list`. now we can do

    helm repo update

The files it add or update is in some other folder. Now we can install the nginx ingress controller.

    helm install quickstart ingress-nginx/ingress-nginx

After a few seconds we can see the ingress controller is running. Then we can use:

    kubectl get svc

From there we can see services of the neginx controller and controller admission, as well as their IPs, PORTs.

### Assign a DNS name

If the kubernetes is run by docker, docker will kindly add below stuff to your `/etc/hosts`

    # Added by Docker Desktop
    # To allow the same kube context to work on the host and the container:
    127.0.0.1 kubernetes.docker.internal

### how to use code to deploy or configure

maybe we need a python env to run python scripts
