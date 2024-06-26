
# CI-CD-todo-api
CI/CD of a django todo api using github actions only 

1. dockerize the app first, have a dockerized todo-app
2. docker run -it -p 8000:8000 asiwomex/todo_api:latest
3. http://localhost:8000

## **Requirements:**
the following are required 
- Existing GitHub repository for your Todo API project.
- An AWS account with an EC2 instance configured for Docker and running a container orchestration tool like Docker Engine or ECS.
- Docker installed and configured on your EC2 instance.
- An SSH key pair created for accessing your EC2 instance securely. Download the private key and keep it secure (**never** commit it to your repository).

In your GitHub repository, navigate to Settings > Secrets and variables > Actions and add the 
following secrets:
1. DOCKER_HUB_USERNAME: Your Docker Hub username.
2. DOCKER_HUB_PASSWORD: Your Docker Hub password.
3. AWS_ACCESS_KEY_ID: Your AWS access key ID.
4. AWS_SECRET_ACCESS_KEY: Your AWS secret access key.
5. EC2_SSH_PRIVATE_KEY: The private SSH key to access your EC2 instance.
6. EC2_PUBLIC_IP: The public IP address of your EC2 instance.
7. EC2_USERNAME: The username to access your EC2 instance (usually ec2-user for 
Amazon Linux)

## Make necessary changes to the main.yaml file, in areas relating to your dockerhub username and app name

1. Push Changes to GitHub: Commit and push your changes to the main branch of your 
GitHub repository.
2. GitHub Actions: GitHub Actions will automatically build the Docker image, push it to 
Docker Hub, and deploy it to your EC2 instance.
3. Check the Running Containers: Connect to your EC2 instance and verify that the Docker 
container is running:
`docker ps`
4. Access the Django API: Open your web browser and navigate to 
http://<EC2_PUBLIC_IP>:8000 to access your Django API.
