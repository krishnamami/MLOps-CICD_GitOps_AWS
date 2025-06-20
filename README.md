# MLOps-CICD_GitOps_AWS 🚀

This project implements a complete **end-to-end MLOps lifecycle** using **modular Python code**, **Docker**, **GitHub Actions**, **AWS ECR**, and **EC2**, with **Airflow** orchestrating periodic model retraining. It demonstrates how to productionize and automate machine learning workflows in a scalable and reusable architecture.

---

## 🔧 Key Features

- ✅ **Modular ML Codebase**: Separate components for ingestion, preprocessing, training, evaluation, and deployment.
- 🐳 **Containerized Pipeline**: Builds a reproducible Docker image for each ML release.
- ⚙️ **CI/CD with GitHub Actions**: On every code commit:
  - Builds Docker image
  - Pushes to AWS ECR
  - Deploys on a self-hosted EC2 machine
- ☁️ **Cloud-Native Execution**: Leverages AWS services like S3, ECR, and EC2.
- 📦 **Artifact Management**: Saves data splits, models, and metadata under an organized `artifacts/` directory.
- ⏱️ **Airflow-Orchestrated Training**: Scheduled training runs automatically store results and trigger model lifecycle pipelines.

---

## 🔁 CI/CD Workflow

1. ✅ **Airflow** triggers periodic training jobs (e.g., daily/weekly).
2. 🧪 Trained models and artifacts are versioned and stored.
3. 💻 Data scientists commit new code/configs to GitHub.
4. 🚀 **GitHub Actions** automatically:
   - Builds a new Docker image
   - Pushes the image to **AWS ECR**
   - Pulls and deploys the image on **EC2** via `docker run`

---

## ⚙️ Technologies Used

| Category          | Tools                         |
|-------------------|-------------------------------|
| Workflow Engine   | Apache Airflow                |
| CI/CD             | GitHub Actions                |
| Containerization  | Docker                        |
| Cloud Services    | AWS ECR, EC2, S3              |
| Model Serving     | Flask                         |
| Language          | Python 3.10                   |

---
![MLOps-CICD_GitOps_AWS 🚀 - visual selection](https://github.com/user-attachments/assets/420865e6-d538-45de-bdad-fe10e2aa4616)




## 🚀 Getting Started

### 🔧 Prerequisites

- AWS account with ECR and EC2 permissions
- GitHub repository secrets configured:
  - `AWS_ACCESS_KEY_ID`
  - `AWS_SECRET_ACCESS_KEY`
  - `AWS_REGION`
  - `ECR_REPOSITORY_NAME`
  - `AWS_ECR_LOGIN_URI`
  - `MONGO_DB_URL` (if used in app)

## Project Structure 

![image](https://github.com/user-attachments/assets/9974e5b8-7e79-4e17-9c65-c2e8c1751a3f)

🧠 Future Enhancements
Integrate Terraform for infrastructure-as-code (ECR, S3, EC2 provisioning)

Add MLflow or DVC for better experiment tracking

Extend to support SageMaker training & model registry

Include monitoring and alerts (e.g., Prometheus + Grafana)

Acknowledgments
This project structure and workflow are inspired by best practices in MLOps and GitOps engineering. Built for scalability, reproducibility, and real-world ML deployment.

