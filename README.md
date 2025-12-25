# CI/CD with GitHub Actions – DevOps Learning Project

## What is CI/CD?

CI/CD stands for **Continuous Integration** and **Continuous Deployment/Delivery**.

- **Continuous Integration (CI)** ensures that every code change is automatically tested and validated before being merged.
- **Continuous Deployment (CD)** automates the process of delivering build artifacts (such as Docker images) so applications can be deployed reliably and consistently.

CI/CD helps companies:
- Catch bugs early
- Reduce manual deployment errors
- Ship features faster
- Maintain consistent and repeatable releases

As part of my DevOps journey, this project helped me understand **how automation connects code to production**.

---

## Project Overview

This repository demonstrates both **CI and CD pipelines** implemented using **GitHub Actions**.

- Task 1 focuses on **code validation and quality checks**
- Task 2 focuses on **automated artifact delivery using Docker**

Each task mirrors real-world DevOps practices.

---

## Task 1 – Continuous Integration (CI)

### What was implemented
A CI pipeline that automatically runs when application code changes.

The pipeline performs:
- **Linting** to enforce code quality
- **Unit tests** to validate functionality
- **Docker build checks** to ensure the image builds successfully

The workflow is triggered on:
- Pushes to `main`
- Pull Requests targeting `main`
- Only when relevant application files change

This avoids unnecessary pipeline runs for documentation-only updates.

---

### Tools Used
- GitHub Actions
- Python
- Ruff (linting)
- Pytest (unit testing)
- Docker

---

### Challenges & Lessons Learned
While implementing CI, I encountered and resolved several real-world issues:

- Workflow not triggering due to incorrect file paths
- Case sensitivity issues (`CICD` vs `cicd`)
- YAML syntax errors caused by small indentation mistakes
- Incorrect trigger configuration causing workflows to run unexpectedly
- Understanding how `paths` filters control when pipelines execute

These challenges reinforced the importance of:
- Attention to detail
- Reading pipeline logs carefully
- Iterative debugging

---

### CI Pipeline Screenshot
⬜ <img width="1920" height="90" alt="image" src="https://github.com/user-attachments/assets/592155f6-d7a6-4af1-9d0c-e007163fca41" />


---

## Task 2 – Continuous Deployment (CD)

### What was implemented
A CD-style workflow that automates Docker image delivery.

The workflow:
- Builds a Docker image from the application
- Tags the image using the Git commit SHA
- Pushes the image to Docker Hub
- Uses GitHub Secrets for secure authentication

This demonstrates how code changes can be transformed into deployable artifacts automatically.

---

### Tools Used
- GitHub Actions
- Docker
- Docker Hub
- GitHub Secrets

---

### Challenges & Lessons Learned
During this task, I learned:

- The importance of separating CI and CD workflows
- How to securely manage credentials using secrets
- Why Docker builds should be validated in pipelines
- How automated delivery reduces deployment risk

This task helped connect **development work to real deployment pipelines**.

---

### CD Pipeline Screenshot
⬜ <img width="1588" height="142" alt="image" src="https://github.com/user-attachments/assets/d9e67839-7352-464c-8507-85ad1277217a" />


---

## What This Project Taught Me

Through these tasks, I gained practical experience with:
- Designing event-driven pipelines
- Debugging CI/CD failures
- Structuring workflows for maintainability
- Applying real-world DevOps best practices

This project forms a strong foundation for future work with:
- Kubernetes
- Cloud deployments (AWS/GCP/Azure)
- Infrastructure as Code
- Advanced CI/CD pipelines

---

## Next Steps
- Extend CD to deploy into a cloud environment
- Add environment-based deployments
- Integrate security scanning into CI
