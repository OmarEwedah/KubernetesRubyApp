# KubernetesRubyApp

# **ruby on rails application running with Kubernetes Using Minikube**

**Prerequisites**

 1. [install git](https://www.linode.com/docs/development/version-control/how-to-install-git-on-linux-mac-and-windows/) 
 2. [install docker](https://rancher.com/docs/rancher/v1.6/en/hosts/)
 3. [install virtualbox](https://www.virtualbox.org/wiki/Downloads)
 4. [install minikube](https://github.com/kubernetes/minikube/releases)
 5. [install kubectl](https://kubernetes-cn.github.io/docs/tasks/tools/install-kubectl/) 

**Clone the code from github**

   

    git clone https://github.com/OmarEwedah/KubernetesRubyApp.git

**Start cluster** 
 run  `minikube start`
			
**NOTE:**  run `eval $(minikube docker-env)`

**Building our Image**

    docker build -t drkiq_ruby KubernetesRubyApp/
**deploy Ruby application on kubernetes**

 1. `kubectl create -f KubernetesRubyApp/kubernetes/secret.yaml`
 
 2. `kubectl create -f KubernetesRubyApp/kubernetes/configmap.yaml`
 
 3. `kubectl create -f KubernetesRubyApp/kubernetes/postgres-pvc.yaml`
 
 4. `kubectl create -f KubernetesRubyApp/kubernetes/postgres-service.yaml`
 
 5.  `kubectl create -f KubernetesRubyApp/kubernetes/postgres.yaml`
 
 6.  `kubectl create -f KubernetesRubyApp/kubernetes/db-job.yaml`
 
 7.  `kubectl create -f KubernetesRubyApp/kubernetes/redis-pvc.yaml`
 
 8.  `kubectl create -f KubernetesRubyApp/kubernetes/redis-service.yaml`
 
 9.  `kubectl create -f KubernetesRubyApp/kubernetes/redis.yaml`
 
 10. `kubectl create -f KubernetesRubyApp/kubernetes/drkiq-service.yaml`
 
 11. `kubectl create -f KubernetesRubyApp/kubernetes/drkiq.yaml`
 
 12. `kubectl create -f KubernetesRubyApp/kubernetes/sidekiq.yaml`
 
 14. `kubectl create -f KubernetesRubyApp/kubernetes/migrate-job.yaml`
