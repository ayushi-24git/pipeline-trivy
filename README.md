
<h1>
Pipeline-trivy

</h1>
This repository demonstrates Trivy, a vulnerability management tool for images and containers. It uses Tekton pipeline under the hood.

The repo contains two tasks. Vulnerable-image pulls a sample image from Dockerhub, which is vulnerable. Task scan-image scans that pulled image through Trivy tool.


<h2>Installing the tasks</h2>  


  `kubectl apply -f https://raw.githubusercontent.com/ayushi-24git/pipeline-trivy/main/tasks/vulnerable-image.yaml`  
  
  `kubectl apply -f https://raw.githubusercontent.com/ayushi-24git/pipeline-trivy/main/tasks/scan-image.yaml`  
  


<h2>Applying pipeline yamls</h2>  


  `kubectl apply -f https://raw.githubusercontent.com/ayushi-24git/pipeline-trivy/main/pipeline.yaml`  
  
  `kubectl apply -f https://raw.githubusercontent.com/ayushi-24git/pipeline-trivy/main/pipelinerun.yaml`  
  
