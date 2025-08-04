Node.js Chat Application with CI/CD
This repository contains a basic real-time chat application built with Node.js, Express, and Socket.IO.

The primary objective of this project was to implement a complete CI/CD pipeline using GitHub Actions to automate the testing, building, and deployment of the application as a Docker image.

CI/CD Pipeline
A CI/CD workflow has been configured using GitHub Actions (.github/workflows/main.yml). This pipeline automates the entire deployment process, ensuring that any new code pushed to the main branch is automatically tested and published.

Pipeline Trigger
The workflow is automatically triggered on every push to the main branch.

Key Automation Steps
Checkout Code: The pipeline begins by checking out the latest version of the repository.

Set Up Environment: It sets up a Node.js environment and installs all the required project dependencies using npm install. Caching is used to speed up this process for future runs.

Run Tests: The npm test command is executed to ensure that the new code passes all tests before proceeding.

Log in to Docker Hub: The workflow securely logs into Docker Hub using credentials stored in GitHub Secrets.

Build and Push Docker Image:

It uses Docker Buildx to build the application into a Docker image based on the provided Dockerfile.

The successfully built image is then tagged with the commit SHA and latest.

Finally, the tagged image is pushed to Docker Hub, making it available for deployment.

This automated process ensures continuous integration and delivery, improving reliability and development speed.
