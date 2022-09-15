# Purpose
The purpose of this repository is to show how automatic build and deployment of sample application can be done in GCP environment, using cloudbuild and GKE.

# Architecture

Demonstration of deploying an application in Google Cloud using Google Kuberentes Engine (GKE).

![gke_app](https://user-images.githubusercontent.com/110168400/190117742-befea741-4fdf-4889-b408-a0b72d7abd42.png)

# Getting Started

1)Ensure the Following APIs are enabled (enable with gcloud services enable [service]):  
    &emsp;Container Registry  
    &emsp;Cloud build  
    &emsp;Kubernetes Api  
2)Create Cloud build trigger to connect to github repo.  
3)Refer cloudbuild.yaml  
4)Update the code and push.  
5)Triggers the build automatically.  

## Run Following commands sequentially  

"************************************"  

"Building docker image from Dockerfile"  

"*****************************************"  

docker build -t gcr.io/nikkigke/hello_nikita .  


"*************************************"

"Pushing docker image to GCR"  

"*****************************************"

docker push gcr.io/nikkigke/hello_nikita  


"***********************************************"  

"Applying kubernetes yaml deployment & Service files"  

"*****************************************"

kubectl apply -f .  


"******************************************"  

"Listing kubernetes pods"  

"*****************************************"  

kubectl get pods  


"*****************************************"  

Listing kubernetes services"  

"*****************************************"  

kubectl get svc  
