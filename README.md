
# 🚀 Multi-Environment CI/CD Pipeline on GCP

This project demonstrates an end-to-end CI/CD pipeline setup on **Google Cloud Platform (GCP)** to automate deployment across **multiple environments** (dev, staging, and prod). It uses **Terraform** for infrastructure provisioning, **Docker** for containerization, and **Cloud Build** for pipeline automation.

---

## 🎯 Objective

To create a scalable, secure, and environment-isolated CI/CD system on GCP that deploys a containerized web application to GKE clusters in dev, staging, and production setups.

---

## 🧰 Tech Stack

- **Google Cloud Platform (GCP)**  
  - GKE (Google Kubernetes Engine)  
  - Cloud Build  
  - Artifact Registry  
  - Cloud SQL  
- **Infrastructure as Code**  
  - Terraform  
- **Containerization & Deployment**  
  - Docker  
  - Kubernetes (YAML & Helm)  
- **Automation & Version Control**  
  - Cloud Source Repositories / GitHub  
  - Bash Scripts  

---

## 📁 Project Structure

```
multi-env-cicd-gcp/
├── app/
│   └── src/
│       └── main.py
├── cloudbuild/
│   ├── cloudbuild-dev.yaml
│   ├── cloudbuild-staging.yaml
│   └── cloudbuild-prod.yaml
├── scripts/
│   ├── setup_env.sh
│   └── deploy.sh
└── terraform/
    ├── dev/
    ├── staging/
    └── prod/
```

---

## ⚙️ Features

- 🔁 CI/CD for dev, staging, and prod via Cloud Build
- 📦 Docker container builds and pushes to Artifact Registry
- ☁️ Terraform-managed infrastructure (GKE, SQL, IAM)
- 🚀 Helm/K8s deployment with version-controlled manifests
- 📊 Horizontal Pod Autoscaling, Probes, and Network Policies

---

## 🚀 Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/rajkumarpawar07/multi-env-cicd-gcp.git
cd multi-env-cicd-gcp
```

### 2. Set Environment Variables

```bash
export PROJECT_ID=your-gcp-project-id
export REGION=your-region
export ENV=dev   # or 'staging' or 'prod'
```

### 3. Enable GCP Services

Enable APIs:

```bash
gcloud services enable \
  cloudbuild.googleapis.com \
  artifactregistry.googleapis.com \
  container.googleapis.com \
  sqladmin.googleapis.com
```

### 4. Provision Infrastructure

```bash
cd terraform/$ENV
terraform init
terraform apply
```

### 5. Trigger Cloud Build Pipeline

```bash
gcloud builds submit --config cloudbuild/cloudbuild-$ENV.yaml
```

---

## 📈 Outcomes

- 🔄 Fully automated deployments with no manual intervention
- 🔐 Isolated environments with secure configurations
- ⚙️ Scalable infrastructure on GKE with minimal downtime

---

## 📚 Learnings

- Practical implementation of **multi-environment CI/CD pipelines**
- Hands-on experience with **Terraform**, **Cloud Build**, **Kubernetes**, and **GKE**
- Gained knowledge of **IaC, GitOps, and container orchestration**

---

## 📎 References

- [Terraform GCP Provider](https://registry.terraform.io/providers/hashicorp/google/latest/docs)
- [GKE Official Docs](https://cloud.google.com/kubernetes-engine/docs)
- [Cloud Build Docs](https://cloud.google.com/build/docs)

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙌 Contributions

Feel free to fork this project and contribute via pull requests. Suggestions, bug reports, and feature requests are welcome!
