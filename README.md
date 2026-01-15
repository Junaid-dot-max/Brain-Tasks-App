🧠 Brain Tasks App – End-to-End DevOps Deployment
This project demonstrates deploying a React application into a production-ready DevOps pipeline using Docker, AWS ECR, AWS EKS, CodeBuild, and CodePipeline.
The goal of this project is to showcase CI/CD automation, containerization, Kubernetes deployment, and AWS cloud services integration.
________________________________________
📌 Application Overview
•	Application: Brain Tasks App (React)
•	Port: 3000
•	Container Runtime: Docker
•	Container Registry: Amazon ECR
•	Orchestration: Amazon EKS (Kubernetes)
•	CI/CD: AWS CodeBuild + AWS CodePipeline
•	Monitoring: Amazon CloudWatch Logs
________________________________________
📂 Repository Structure
.
├── Dockerfile
├── nginx.conf
├── buildspec.yml
├── deployment.yaml
├── service.yaml
├── dist/
└── README.md
________________________________________
🐳 Dockerization
The React application is built and served using Nginx inside a Docker container.
Dockerfile
•	Uses nginx:alpine
•	Serves production build from /usr/share/nginx/html
•	Exposes port 3000
  ________________________________________
📦 Amazon ECR (Elastic Container Registry)
•	An ECR repository was created to store Docker images
•	Docker image was tagged and pushed to ECR

  ________________________________________
☸️ Kubernetes Deployment (Amazon EKS)
EKS Cluster
•	EKS cluster created using eksctl
•	Worker nodes provisioned successfully
     ________________________________________
Kubernetes Resources
•	Deployment: Defines application pods
•	Service: Exposes application using LoadBalancer
kubectl get pods
kubectl get svc
    
[SCREENSHOT: Application LoadBalancer URL]
Filename: 08_App_LoadBalancer_URL.png
________________________________________
🔄 CI/CD with AWS CodeBuild
CodeBuild Project
•	Source: GitHub repository
•	Build environment: Managed image
•	Build logic defined in buildspec.yml
Build Actions
•	Login to Amazon ECR
•	Build Docker image
•	Push Docker image to ECR
              
________________________________________
🔁 CI/CD with AWS CodePipeline
Pipeline Stages
1.	Source
o	GitHub (via GitHub App)
2.	Build
o	AWS CodeBuild project
3.	Deploy
o	Skipped (Application already deployed to EKS)
The pipeline automatically triggers on every push to the GitHub repository.
     

________________________________________
📊 Monitoring & Logs (CloudWatch)
•	Build logs monitored using Amazon CloudWatch
•	CodeBuild logs available under /aws/codebuild/brain-tasks-build
 ________________________________________
✅ Final Outcome
•	Application successfully deployed on AWS EKS
•	Docker image stored in Amazon ECR
•	CI pipeline implemented using CodeBuild
•	End-to-end automation using CodePipeline
•	Logs monitored via CloudWatch
________________________________________
🧠 Key Learnings
•	Dockerizing frontend applications
•	Working with AWS ECR and EKS
•	Writing Kubernetes manifests
•	Implementing CI pipelines using CodeBuild
•	Orchestrating CI with CodePipeline
•	Debugging real-world CI/CD issues
________________________________________
🧹 Cleanup (Optional – After Submission)
To avoid AWS charges:
eksctl delete cluster --name brain-tasks-cluster --region ap-south-1
________________________________________
✍️ Author
Junaid Ahamed
DevOps | Cloud | Kubernetes | AWS

