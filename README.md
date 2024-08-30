# GitOps-and-ArgoCD-with-circleci-docker-Terraform-and-AWS

# Architecture:

<img width="1155" alt="Screenshot 2024-08-30 at 20 45 42" src="https://github.com/user-attachments/assets/bef6593e-6472-4563-8803-ccc4921ffa61">


# Steps:

This project starts when a developer does a code commit into the requested branch in the GitHub repository. The code is pulled by a pipeline. I will use circle ci as ci tool. The pipeline will test, build .There will be a Dockerfile that will push the image to docker registry such as Docker Hub with a TAG that updates the manifest file and ends the changes to ArgoCD. This will push all the changes to Kubernetes cluster. We have a controlplane component in the upper right part of the diagram deployed in 3 Availability Zones and 2 worker nodes deployed in 2 availability zones with NA gateways, and load balancers... ArgoCD will update these pods that are running as part of our app and these parts are exposed as a service. We will interact with the cluster using kubectl.

First, we create a user that manages resources from Terraform:



<img width="879" alt="Screenshot 2024-08-30 at 20 59 38" src="https://github.com/user-attachments/assets/b1bc49a6-6624-45a9-8f26-5e8b7cb6830e">



<img width="991" alt="Screenshot 2024-08-30 at 20 59 55" src="https://github.com/user-attachments/assets/ccda28cf-f277-498b-942c-c5dd48e1cac8">

We click Attach policies directly and put admin level permissions


we create access key with CLI 

<img width="744" alt="Screenshot 2024-08-30 at 21 03 06" src="https://github.com/user-attachments/assets/0b906005-98d7-4ea1-83ec-1a3a7a585390">



We go to Visual Code and use aes configure:

<img width="731" alt="Screenshot 2024-08-30 at 21 04 37" src="https://github.com/user-attachments/assets/dbc7e8f0-8e91-44fb-a7e5-53cd41b723ae">

