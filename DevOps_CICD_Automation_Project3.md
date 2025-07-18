
# Project 3: Implement DevOps CI/CD Pipeline for Mentorbabaa Quiz App

## Objective
Design and implement an automated CI/CD pipeline to build, test, containerize, and deploy the quiz app on AWS.

---

## Functional Requirements

### 1. Source Control Integration
- Use Git (GitHub, GitLab, or Bitbucket) for code repository.
- Branching strategy for feature, develop, and main/master branches.

### 2. Continuous Integration (CI)
- Jenkins pipeline triggers on code commits or pull requests.
- Automated unit tests and code quality checks.
- Build Docker images of the Flask app.

### 3. Containerization
- Dockerfile to containerize the app.
- Tag Docker images with version and commit info.
- Push images to container registry (AWS ECR or Docker Hub).

### 4. Continuous Deployment (CD)
- Deploy Docker containers to AWS (EC2 with Docker, ECS, or EKS).
- Automated rollback on failed deployments.
- Notifications on deployment status via email/Slack.

---

## Non-Functional Requirements

### 1. Reliability
- Pipeline must handle errors gracefully and notify stakeholders.
- Pipeline stages should be idempotent and retryable.

### 2. Security
- Store credentials securely (Jenkins credentials store or AWS Secrets Manager).
- Use least privilege principles for deployment agents.

### 3. Maintainability
- Modular Jenkinsfile with stages clearly defined.
- Documentation of pipeline steps and troubleshooting.

### 4. Performance
- Pipeline run time optimized for faster feedback (ideally < 10 minutes).

---

## Deliverables
- Jenkinsfile defining the CI/CD pipeline.
- Dockerfile for containerization.
- Deployment scripts/configuration for AWS target.
- Documentation detailing pipeline setup and usage.

---

## Timeline
- Week 1: Set up Jenkins integration and build.
- Week 2: Containerize and automate image publishing.
- Week 3: Automate deployment and add rollback.
- Week 4: Documentation and pipeline stabilization.
