# ML Deployment Demo

A minimal example of deploying a machine learning inference application using Docker and GitHub Actions for CI/CD. 
This repository demonstrates best practices in containerization, reproducibility, and automation for model deployment.

---

## 📁 Project Structure

---

## 🧪 What This Project Demonstrates

- Minimal ML inference function (`Hello, Inference!`)
- Unit test integration using `pytest`
- Docker-based environment with optional CUDA GPU support
- GitHub Actions CI/CD pipeline
  - Run tests on push
  - Build Docker image automatically

---

## 🔧 Prerequisites

- [Python 3.8+](https://www.python.org/)
- [Docker](https://www.docker.com/)
- [Git](https://git-scm.com/)
- Optional (for GPU): NVIDIA GPU with drivers and [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html)

---

## 🚀 Quickstart

### 1. Clone the repository

```bash
git clone https://github.com/your-username/ml-deployment-demo.git
cd ml-deployment-demo
```
---

### 2. Set up a Python environment
#### Using conda:
```bash
conda create -n deploy-env python=3.8 -y
conda activate deploy-env
pip install -r requirements.txt
```

#### or using virtualenv:
``` bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### 3. Run the Inference Script
``` bash
python app/infer.py
```

### 4. Run Tests
``` bash
pytest tests/
```

### Build & Run with Docker
#### Build the Docker Image
``` bash
docker build -t ml-deployment-demo .
```

### Run the Container
``` bash
docker run --rm ml-deployment-demo
```
### if using GPU
``` bash
docker run --gpus all --rm ml-deployment-demo
```

### CI/CD with GitHub Actions
The CI/CD pipeline is defined in .github/workflows/deploy.yml. It will:
- Run pytest on every push and pull_request
- Build the Docker image
  
``` bash
git add .
git commit -m "Trigger CI/CD"
git push
```

