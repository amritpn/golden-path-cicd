# 🛤️ Golden Path CI/CD Platform

A fully managed CI/CD service providing secure-by-default, reusable, and governed delivery workflows for all engineering teams. No repo-level configuration required — all OIDC, roles, policies, and security controls are centrally managed by the Platform Team.

---

## 🚀 What This Platform Provides

### **How We Build**
Reusable workflows for:
- Docker-based services  
- Java + Maven  
- Node + NPM  
- Python (optional)  
- Go (optional)

### **How We Deploy**
Golden path deployment workflows for:
- **AWS ECS** (Fargate)  
- **AWS EKS** (Kubernetes)  
- **AWS Lambda** (serverless)

### **How We Secure**
Security baked into every workflow:
- **AWS X-Ray** scanning  
- **GitHub Advanced Security (GHAS)**  
- **Dependency scanning**  
- **Container scanning**  
- **Secrets detection**

### **How We Govern**
Platform-level governance:
- No direct internet access  
- All downloads proxied via **JFrog**  
- Mandatory OIDC roles (centrally managed)  
- Policy-as-code checks  
- Audit logs and compliance reporting

---

## 🧩 How Teams Use This

Calling repos simply reference the reusable workflow:

```yaml
name: Build & Deploy

on:
  push:
    branches: [ main ]

jobs:
  ci-cd:
    uses: amritpn/golden-path-cicd/.github/workflows/platform-ci.yml@main
    with:
      service_name: "orders-api"
      runtime: "java-maven"
      deploy_target: "ecs"
