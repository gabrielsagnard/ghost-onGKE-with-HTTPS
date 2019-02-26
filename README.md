# Ghost-onGKE-with-HTTPS
Déployer votre blog sous Ghost depuis GKE (K8S) avec du HTTPS

# Create a cluster on GKE

    gcloud init
    gcloud config set project [votre projet]
    gcloud config set compute/region europe-west1
    gcloud config set compute/zone europe-west1-c

Puis, 

     gcloud container clusters create ghost-cluster   --enable-cloud-logging   --enable-cloud-monitoring   --subnetwork default
     
     gcloud container clusters get-credentials ghost-cluster
     
# Installer Helm 

- sur MacOS :

        brew install kubernetes-helm
        kubectl create serviceaccount --namespace kube-system tiller
        kubectl create clusterrolebinding tiller-cluster-rule --clusterrole=cluster-admin --serviceaccount=kube-system:tiller
        helm init --service-account tiller
    
# Installer Nginx ingress controller

Via Helm

    helm install stable/nginx-ingress --namespace kube-system
    
Le reste se trouve dans l'article du blog : 

http://blog.gsagnard.fr/utiliser-cert-manager-pour-securiser-votre-blog-deploye-sous-gke/
    
