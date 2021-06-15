
<h1>
Pipeline-trivy

</h1>
This repository demonstrates Trivy, a vulnerability management tool for images and containers. It uses Tekton pipeline under the hood.  



The repo contains a single task, **scan-image**, for scanning an image through Trivy. After running the pipeline, user is first asked to enter an image to be scanned. Try **vulnerables/web-dvwa:1.9**. It is a sample vulnerable image available at DockerHub. Further working of Trivy can be understood [here](https://rastogee-ayushi.medium.com/trivy-keep-your-artifacts-vulnerability-free-6dce292134e5). 

## Setting up cluster
Set up a cluster using minikube by doing a minikube start.

## Setting up Tekton
Install tekton with the following command after setting up the cluster

kubectl apply --filename https://storage.googleapis.com/tekton-releases/pipeline/latest/release.yaml

This will install all the necessary Tekton components to get started.

## Applying the Tasks and Pipeline yamls
Apply all the mentioned tasks in the repositorry above. Example format:

kubectl apply -f https://raw.githubusercontent.com/ayushi-24git/pipeline-trivy-tekton/main/tasks/scan-image.yaml

Apply the pipeline yamls as:

kubectl apply -f https://raw.githubusercontent.com/ayushi-24git/pipeline-trivy-tekton/scan-pipeline-image.yaml

kubectl apply -f https://raw.githubusercontent.com/ayushi-24git/pipeline-trivy-tekton/scan-pipelinerun-image.yaml

Now, start the pipeline by: `tkn pipeline start scan-pipeline-image`


Check logs
Now, the pipeline has successfully started. You can check the logs using the following command:

`tkn pipelinerun logs <name-of-the-pipelinerun>`

You can see the table of all vulnerabilities (if any) detected by Trivy.


  



  
