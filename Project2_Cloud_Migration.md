# Project 2: Migrate and Deploy Mentorbabaa Quiz App on AWS

## Objective
Deploy the full-stack quiz app on AWS leveraging EC2 for the backend app and RDS for MySQL database, ensuring scalability and security.

---

## Functional Requirements

### 1. Infrastructure Setup
- Provision EC2 instance to host Flask app.
- Provision Amazon RDS MySQL instance for the database.
- Configure security groups to allow communication between EC2 and RDS.

### 2. Application Deployment
- Deploy Flask app on EC2 with necessary environment variables (DB host, user, password).
- Ensure app starts on instance boot (use systemd or similar).
- Enable HTTPS access via Elastic Load Balancer or configure SSL.

### 3. Database Migration
- Migrate existing database schema and data to Amazon RDS.
- Provide scripts or manual steps for migration.

### 4. Monitoring & Backup
- Setup basic CloudWatch alarms for EC2 and RDS health.
- Configure automatic RDS backups and snapshots.

---

## Non-Functional Requirements

### 1. Scalability
- Architecture should allow vertical or horizontal scaling.
- EC2 instance type selected based on load estimates.

### 2. Availability
- Aim for minimum downtime during deployment.
- Use multi-AZ RDS deployment for high availability (optional).

### 3. Security
- EC2 and RDS access restricted using security groups.
- Use IAM roles for EC2 to access AWS resources securely.
- Store sensitive data in AWS Secrets Manager or Parameter Store (optional).

### 4. Maintainability
- Use Infrastructure as Code (IaC) tools if possible (CloudFormation/Terraform).
- Documentation of deployment and rollback procedures.

---

## Deliverables
- Architecture diagram.
- Deployment scripts or detailed manual steps.
- Updated README with AWS deployment instructions.
- Verification report of successful deployment.

---

## Timeline
- Week 1: Provision AWS EC2 and RDS.
- Week 2: Deploy application and migrate database.
- Week 3: Configure monitoring, backup, and security.
