# Image segmentation model-serving on Google Kubernetes Engine
![](/images/webapp.png)

This repository is an enhanced version of the original [project](https://davidefiocco.github.io/streamlit-fastapi-ml-serving), which demonstrates the usage of Streamlit and FastAPI for serving a machine learning-based image semantic segmentation model. The primary objective of this repository is to deploy the application on [Google Kubernetes Engine](https://cloud.google.com/kubernetes-engine) for increased scalability and reliability.

While the original project focused on providing both a backend API and a frontend interface for users, this repository extends the functionality by incorporating deployment on GKE. By leveraging GKE's managed Kubernetes service, we ensure efficient container orchestration and enable seamless scaling of the application.

In this enhanced version, we have adapted the original codebase to support deployment on GKE. The repository includes the necessary configuration files, such as Kubernetes deployment manifests and associated resources, which can be easily managed and deployed using the Cloud Code extension within Visual Studio Code.
The [image semantic segmentation model](https://pytorch.org/hub/pytorch_vision_deeplabv3_resnet101/) is served using `FastAPI` for the backend service and `streamlit` for the frontend service. 

## Steps to deploy the web application on GKE
1. Clone the repo
```
git clone https://github.com/chandrakanth-jp/image-segmentation-gke-webapp.git
```
2. Go to the folders 'fastapi' and 'streamlit' and build docker images 
```
docker build -t fastapi
docker build -t streamlit
```
3.Set up GKE Cluster using Cloud Code Extension:
- Install the Cloud Code extension in Visual Studio Code
- Use the Cloud Run extension to set up a GKE cluster

    ![](/images/select_platform.png)

- Follow the extension's prompts and configure the cluster
-  Specify the necessary deployment configurations, such as the number of replicas and resource allocation

    ![](/images/create_cluster.png)
    
4. Run the application on the cluster
- Use the Cloud Code extension to deploy the application to the GKE cluster

    ![](/images/run.png)
    
Once the application is deployed on the GKE cluster, you can access and interact with it using the specified URL or IP address.
