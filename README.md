# vehicle-insurance-mlops
made project on vehicle insurance and made use of principles of mlops


# Vehicle Project 🚗

End-to-end **Machine Learning + MLOps pipeline** with FastAPI, MongoDB Atlas, AWS, and CI/CD using GitHub Actions + EC2 + ECR.

---

## 📌 Features
- Local package setup with `setup.py` & `pyproject.toml`
- Virtual environment & dependency management
- MongoDB Atlas integration for data storage
- Logging, exception handling, and notebooks for EDA
- Modular pipeline:
  - Data Ingestion
  - Data Validation
  - Data Transformation
  - Model Training, Evaluation & Pusher
- AWS Integration:
  - S3 for model storage
  - ECR for Docker images
  - EC2 for deployment
- CI/CD pipeline with GitHub Actions and self-hosted runner
- FastAPI app exposed on EC2 instance

---

## ⚙️ Setup Instructions

### 1. Environment
```bash
conda create -n vehicle python=3.13 -y
conda activate vehicle
pip install -r requirements.txt



2. MongoDB Atlas

Create cluster → Add user → Allow IP 0.0.0.0/0

Get connection string & set environment variable:
bash:
export MONGODB_URL="mongodb+srv://<username>:<password>@cluster-url"

3. AWS Setup

Create IAM user & S3 bucket (my-model-mlopsproj)

Create ECR repo: vehicleproj

Launch EC2 instance (Ubuntu) and install Docker

Configure GitHub secrets:

AWS_ACCESS_KEY_ID

AWS_SECRET_ACCESS_KEY

AWS_DEFAULT_REGION

ECR_REPO

4. Run Locally
python app.py
# or
uvicorn app:app --host 0.0.0.0 --port 5000

5. Deployment

CI/CD runs on push to main

Docker image pushed to ECR

Container deployed on EC2 (port 5000)

Access app at:

http://<EC2_PUBLIC_IP>:5000

📂 Project Structure
.
├── src/                 # Source code
├── entity/              # Configs & artifacts
├── components/          # Pipeline components
├── notebook/            # Jupyter notebooks
├── app.py               # FastAPI app
├── requirements.txt
├── setup.py
├── pyproject.toml
└── .github/workflows/   # CI/CD configs
