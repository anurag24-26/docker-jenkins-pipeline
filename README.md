# Jenkins + Docker + DockerHub Automation

This project demonstrates an automated pipeline that:
- Builds a Docker image
- Pushes it to Docker Hub
- Managed by Jenkins

## Steps
1. Clone this repo to your GitHub
2. Create a Jenkins pipeline pointing to it
3. Add DockerHub credentials in Jenkins (ID: `dockerhub-login`)
4. Run the pipeline → It will push the image to your DockerHub.
