# Microservices CI/CD Lab

[![License](https://img.shields.io/badge/license-MIT-blue)]()
[![Version](https://img.shields.io/badge/version-v1.0.0-brightgreen)]()

A comprehensive **DevOps lab** demonstrating **end-to-end CI/CD pipelines** for microservices across multiple languages and deployment environments.  
This project showcases both **offline and online CI/CD workflows**, with automated build, deployment, testing, rollback, and reporting mechanisms.

---

## 🎯 Project Overview

Modern microservices architectures require robust CI/CD pipelines to ensure consistent deployments, automated testing, and rapid rollback when issues occur.  
This repository provides a structured showcase of these capabilities:

- **Offline Jenkins-based CI/CD** for air-gapped environments
- **GitHub Actions workflows** for cloud and online environments
- **GitLab CI pipelines** for self-hosted private runners
- **ArgoCD GitOps deployment** for declarative continuous delivery
- **Docker/Kubernetes integration** for containerized microservices
- **Automated testing & reporting** to ensure deployment health

> This lab is designed as a **reference and learning project**, suitable for engineers, DevOps practitioners, and freelancers demonstrating production-grade pipeline expertise.

---

## 🚀 Project Roadmap

| Version / Branch | Description | Status |
|-----------------|-------------|--------|
| `v1-offline-jenkins` | Fully offline Jenkins pipeline with local Docker/K8s deployment and automated test reporting | ✅ Stable |
| `v2-github-actions` | GitHub Actions CI/CD workflow for FastAPI microservices | 🔄 Planned |
| `v3-gitlab-ci` | Private GitLab CI pipeline with self-hosted runner | 🔄 Planned |
| `v4-argocd-gitops` | Declarative GitOps deployment with ArgoCD | 🔄 Planned |
| `v5-harbor-airgap` | Enterprise offline deployment with internal Docker registry | 🔄 Planned |

---

## 🗂️ Repository Structure

```
microservices-ci-cd-lab/
├── README.md
├── docs/                     # Documentation for each workflow
├── app/                      # Microservices code (FastAPI initial demo)
│   ├── main.py
│   ├── requirements.txt
│   └── tests/
├── docker/                   # Dockerfiles and build scripts
├── k8s/                      # Kubernetes manifests
├── pipeline/                 # CI/CD pipeline scripts (Jenkins, GH Actions, GitLab)
└── versions/                 # Versioned branches or release snapshots
```

---

## ⚙️ Usage (v1-offline-jenkins)

1. **Prepare environment:**
   - Kind cluster or local Kubernetes
   - Jenkins installed locally (offline)
   - Python ≥ 3.10

2. **Build Docker image:**
```bash
cd docker
./build.sh
```

3. **Load image into Kind cluster:**
```bash
kind load docker-image fastapi-demo:v1.0.0 --name microservices-cluster
```

4. **Deploy to Kubernetes:**
```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
```

5. **Run pipeline:**
```bash
cd pipeline
./pipeline.sh
```

6. **Check test report:**
```bash
cat reports/test-report-v1.0.0.md
```

---

## 🌟 Key Features

- End-to-end CI/CD automation for microservices
- Offline and online deployment workflows
- Automated self-checks, rollback, and reporting
- Extensible structure for multiple languages and microservices
- Production-grade design for both freelancers and enterprise engineers

---

## 📌 Contribution / Expansion Plan

- Extend pipeline for additional languages (Java/Spring Boot, Node.js, Go)
- Add advanced testing scenarios and monitoring integration
- Integrate GitOps and private registry workflows
- Document best practices for production-grade DevOps

---

## 📄 License

MIT License © 2025 Sterling Aureum
