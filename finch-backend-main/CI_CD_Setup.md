# CI/CD Setup for Finch Backend

This document describes the CI/CD pipeline configured using GitHub Actions for the Finch Backend.

## Workflow Triggers

- The workflow runs on every `push` branch.

## Jobs

### 1. Build and Test

- Checks out code.
- Sets up Node.js.
- Installs dependencies.
- Runs lint checks and unit tests.

### 2. Docker Build and Push

- Builds a Docker image from the backend source code.
- Pushes the image to Docker Hub.
- Uses the Docker username and password stored as GitHub Secrets.

## Docker Image

- Docker image is tagged and pushed to:  
  `docker.io/your-dockerhub-username/finch_backend:latest`

## Secrets Used

- `DOCKER_USERNAME` - Your Docker Hub username
- `DOCKER_PASSWORD` - Your Docker Hub password or token

## Notes

- Make sure the secrets are added to GitHub under Settings → Secrets and Variables → Actions.
