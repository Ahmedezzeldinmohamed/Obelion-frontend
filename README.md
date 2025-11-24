Obelion Cloud Automation Assessment - Frontend Uptime Kuma Repository

This repository covers the requirements for Task Group B-1: Automated CI/CD for the Frontend application, using the Uptime Kuma public image as specified.

1. Task Group B-1: Automated Deployment

The pipeline is configured in .github/workflows/deploy.yml.

Deployment Flow:

Trigger: Push to main branch.

Build Step: A placeholder command (echo building.....) is executed to satisfy the CI build requirement.

Deployment: The workflow connects via SSH to the Frontend EC2 server.

Docker Deployment: The script pulls the latest louislam/uptime-kuma:latest image and runs it using docker-compose up -d --force-recreate on port 3001.

2. Configuration (GitHub Secrets)

The same SSH secrets used for the backend deployment are required here, targeting the Frontend EC2 instance:

Secret Name

Description

SSH_HOST_FRONTEND

Public IP address of the Frontend EC2 instance.

SSH_USER_FRONTEND

SSH username (e.g., ubuntu).

SSH_PRIVATE_KEY_FRONTEND

The private SSH key used to authenticate with the EC2 server.
