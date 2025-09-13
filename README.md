# Azure DevOps HTML Site

A demonstration project showcasing the deployment of a static HTML site using Azure DevOps pipelines.

---

## Features

- CI/CD Pipelines: Automated workflows for building, testing, and deploying static websites.
- Docker Integration: Uses Docker for consistent build and deployment environments.
- Azure Deployment: Deploys the static site to Azure Web Apps.

---

## Prerequisites

- Azure Subscription: Required for resource provisioning.
- GitHub Repository: For storing code and configuration files.
- Azure DevOps Account: For managing pipelines and deployments.
- Docker: For containerizing the application.
- Azure CLI: Command-line interface for managing Azure resources.

---

## Setup & Configuration

### 1. Clone the Repository
```bash
git clone https://github.com/ca5ual/azure-devops-html-site.git
cd azure-devops-html-site
```

### 2. Build the Docker Image
```bash
docker build -t azure-devops-html-site .
```

### 3. Run the Docker Container Locally
```bash
docker run -p 8080:80 azure-devops-html-site
```
Access the site at [http://localhost:8080](http://localhost:8080).

### 4. Push the Docker Image to Azure Container Registry
```bash
az acr login --name <your-registry-name>
docker tag azure-devops-html-site <your-registry-name>.azurecr.io/azure-devops-html-site:v1
docker push <your-registry-name>.azurecr.io/azure-devops-html-site:v1
```

### 5. Deploy to Azure Web App
Create a Web App in Azure and configure it to pull the Docker image from your Azure Container Registry.

---

## Usage

- CI/CD Pipelines: Automatically build and deploy the static site on code changes.
- Docker Integration: Ensure consistent environments across development and production.
- Azure Deployment: Leverage Azure's scalability and reliability for hosting static sites.

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

