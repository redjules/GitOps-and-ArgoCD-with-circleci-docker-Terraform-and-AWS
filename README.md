# GitOps-and-ArgoCD-with-circleci-docker-Terraform-and-AWS

# Architecture:

<img width="1155" alt="Screenshot 2024-08-30 at 20 45 42" src="https://github.com/user-attachments/assets/bef6593e-6472-4563-8803-ccc4921ffa61">


# Steps:

This project starts when a developer does a code commit into the requested branch in the GitHub repository. The code is pulled by a pipeline. I will use circle ci as ci tool. The pipeline will test, build .There will be a Dockerfile that will push the image to docker registry such as Docker Hub with a TAG that upates the manifest file adns edns the changes to ArgoCD. This will push all the changes to Kuberenetes cluster. We have a controlplane component in the upper right part of the diagram that is deployed in 3 Availability Zones and we have 2 worker nodes deployed in 2 availability zones with nate gateways, load balancers... ArgoCD will update these pods that are running as part of our app and these parts are exposed as a service. We will interact with the cluster using kubectl.

First we create a user that manages resources from Terraform.

<img width="879" alt="Screenshot 2024-08-30 at 20 59 38" src="https://github.com/user-attachments/assets/b1bc49a6-6624-45a9-8f26-5e8b7cb6830e">


<img width="991" alt="Screenshot 2024-08-30 at 20 59 55" src="https://github.com/user-attachments/assets/ccda28cf-f277-498b-942c-c5dd48e1cac8">


<img width="699" alt="Screenshot 2024-08-30 at 21 00 09" src="https://github.com/user-attachments/assets/3c9c7ef1-a9ca-4ab1-94a7-d1d40e206f27">
