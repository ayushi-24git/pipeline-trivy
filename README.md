
<h1>
Pipeline-trivy

</h1>
This repository demonstrates Trivy, a vulnerability management tool for images and containers. The elaborate working can be understood [here](https://rastogee-ayushi.medium.com/trivy-keep-your-artifacts-vulnerability-free-6dce292134e5).  


The repo contains a single task, **scan-image**, which scans the given image through Trivy tool.

If you have **minikube** on your laptop, do a `minikube start` and run the following commands:

<h2>Installing the tasks</h2>  


  `kubectl apply -f https://raw.githubusercontent.com/ayushi-24git/pipeline-trivy/main/tasks/vulnerable-image.yaml`  
  
  `kubectl apply -f https://raw.githubusercontent.com/ayushi-24git/pipeline-trivy/main/tasks/scan-image.yaml`  
  


<h2>Applying pipeline yamls</h2>  


  `kubectl apply -f https://raw.githubusercontent.com/ayushi-24git/pipeline-trivy/main/pipeline.yaml`  
  
  `kubectl apply -f https://raw.githubusercontent.com/ayushi-24git/pipeline-trivy/main/pipelinerun.yaml`  
  
After applying the above, you can start the Tekton pipeline by running `tkn pipeline start scan-pipeline-image`. After this, the pipeline starts and you will be prompted to enter the image you want to scan. Try **vulnerables/web-dvwa:1.9**. It is a sample vulnerable image available at DockerHub. Check for the logs and you can see the table of all vulnerabilities detected by Trivy.


  
