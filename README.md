🚀 Deploying a Hotstar Clone Using GitHub Actions CI/CD with Docker, Terraform, Kubernetes & SonarQube


In today’s fast-paced DevOps world, automating your deployments is essential. This blog will walk you through how to deploy a Hotstar clone using GitHub Actions for CI/CD, Docker for containerization, Terraform for infrastructure provisioning, Kubernetes for orchestration, and SonarQube for code quality analysis.

🧰 Tech Stack Used
•	GitHub Actions – For CI/CD pipeline automation
•	Docker – For containerizing the app
•	SonarQube – For static code analysis and code quality checks
•	Terraform – For provisioning cloud infrastructure
•	Kubernetes (kubectl) – For deploying containers in production
•	AWS (EC2 + EKS) – As the cloud infrastructure (can be adapted to other clouds)
________________________________________
🗂️ Project Structure
The Hotstar clone project is organized into:
•	A React-based frontend
•	A Node.js backend
•	Dockerized full-stack application
•	Terraform scripts to provision Kubernetes (EKS) infrastructure
•	Kubernetes manifests to manage app deployment
•	A GitHub Actions workflow to automate CI/CD pipeline
•	A SonarQube configuration for static code analysis
________________________________________
⚙️ DevOps Workflow Overview
1.	Developer pushes code to the main branch on GitHub.
2.	GitHub Actions pipeline automatically triggers:
o	Code checkout and environment setup
o	SonarQube scan for bugs, code smells, vulnerabilities
o	Docker image build and push to a registry (e.g., Docker Hub)
o	Kubernetes deployment update using kubectl
3.	Application is deployed to AWS EKS cluster using updated image.
________________________________________
🔐 Secure Secrets Management
All sensitive credentials and access tokens are stored securely in GitHub Actions Secrets:
•	AWS credentials (for Terraform & EKS)
•	Docker Hub credentials
•	SonarQube token
•	Kubernetes config 
This ensures that no sensitive data is hardcoded in the pipeline.
________________________________________
🧠 Infrastructure Automation with Terraform
Terraform is used to automate the provisioning of:
•	VPC, Subnets, and IAM roles
•	Amazon EKS cluster
•	Worker nodes (auto-scaling)
•	Security groups and IAM policies
This guarantees a repeatable and consistent infrastructure setup across environments (dev, staging, prod).
________________________________________
📦 Containerization with Docker
Both frontend and backend are containerized into separate Docker images or a single image depending on the architecture. This provides:
•	Portability between environments
•	Easy rollbacks with versioned images
•	Clean, isolated execution
These images are pushed to Docker Hub (or any container registry) as part of the pipeline.
________________________________________
☸️ Kubernetes Deployment
The Kubernetes manifests include:
•	Deployment objects to manage pods and replica sets
•	Service objects to expose the app internally or externally
•	Optional: Ingress configuration for custom domains and HTTPS
The GitHub Actions workflow uses kubectl to apply changes directly to the EKS cluster after the image is pushed.
________________________________________
🧪 Code Quality with SonarQube
SonarQube is integrated into the CI process to ensure:
•	Static code analysis for bugs, code smells, security hotspots
•	Enforced code quality gates before deployment
•	Visibility into code health via dashboards and reports
This is essential for DevSecOps and maintaining clean, secure code over time.
________________________________________
📈 Monitoring & Observability (Optional Add-ons)
For production-grade deployments, you can extend this pipeline with:
•	Prometheus & Grafana for metrics and performance dashboards
•	ELK or Loki stack for centralized logging
•	ACM + NGINX Ingress for HTTPS support
________________________________________
🎯 Final Outcome
By the end of this setup, you’ll have:
•	A production-ready CI/CD pipeline
•	Fully containerized application
•	Infrastructure-as-Code (IaC) with Terraform
•	Code automatically scanned and analyzed by SonarQube
•	App deployed to a Kubernetes cluster on AWS
________________________________________
📌 Benefits of This Architecture
✅ 100% Automated Code → Deploy Flow
✅ Scalable & Secure Production Setup
✅ Fast Feedback with SonarQube Reports
✅ Reusable Infrastructure Modules (Terraform)
✅ Zero-downtime Deployments via Kubernetes

