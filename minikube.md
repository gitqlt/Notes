minikube: Run a Kubernetes cluster locally
====

**(default driver: docker. Will create one single container)**

**Creating a minikube cluster for testing**

    $ minikube start --cpus=4 --memory=6g --addons=ingress
    $ kubectl get nodes
    $ kubectl get pods
    $ kubectl get pods --all-namespaces
    $ ( docker volume inspect minikube )
      
**Iiii**

    $ iii
