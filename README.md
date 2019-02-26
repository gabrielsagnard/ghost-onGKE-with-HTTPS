# ghost-onGKE-with-HTTPS
Déployer votre blog sous Ghost depuis GKE (K8S) avec du HTTPS

# Create a cluster on GKE

    gcloud init
    gcloud config set project [votre projet]
    gcloud config set compute/region europe-west1
    gcloud config set compute/zone europe-west1-c
