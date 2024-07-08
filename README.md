# Full-Stack FastAPI and React Template

Welcome to the Full-Stack FastAPI and React template repository. This repository serves as a demo application for interns, showcasing how to set up and run a full-stack application with a FastAPI backend and a ReactJS frontend using ChakraUI.

## Project Structure

The repository is organized into two main directories:

- **frontend**: Contains the ReactJS application.
- **backend**: Contains the FastAPI application and PostgreSQL database integration.

Each directory has its own README file with detailed instructions specific to that part of the application.

## Getting Started

To get started with this template, please follow the instructions in the respective directories:

- [Frontend README](./frontend/README.md)
- [Backend README](./backend/README.md)
## Dockerize the Application
- **Frontend**:
  - Create a Dockerfile:
  - Set up a multi-stage Dockerfile to build the frontend and serve it using Nginx.
- **Backend**:
  - Create a Dockerfile:
  - Use a base image that supports FastAPI and Uvicorn.
  - Copy application files and install dependencies.
## Set Up Docker Compose
- Create docker-compose.yml:
- Define services for frontend, backend, database, Adminer, and Traefik.
- Use environment variables from the .env file.
- Configure Traefik labels for routing.
## Configure Traefik
- **Traefik Configuration**:
- Enable Traefik in Docker Compose with necessary entrypoints and providers.
- Set up Traefik labels for frontend, backend, and Adminer to route traffic correctly.
## Launch an EC2 Instance on AWS
- Launch a new EC2 instance.
- Choose an appropriate Amazon Machine Image (AMI).
- Select an instance type (e.g., t2.micro for free tier).
- Configure Instance Settings:
- Add storage as needed.
- Set up security groups to allow traffic on necessary ports (e.g., 80, 443, and 8080).
- Launch and Connect
- Launch the instance and connect via SSH using the key pair you configured.
## Install Docker and Docker Compose on EC2
- Install Docker:
```sh
sudo apt update
sudo apt install docker.io
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker $USER
```
- Install Docker Compose:
```bash
Copy code
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```
## Deploy the Application
- Clone Your Repository:
```bash
Copy code
git clone https://github.com/your-username/your-repo.git
cd your-repo
```
- Run Docker Compose:
```bash
Copy code
docker-compose up -d
```
## Set Up DNS and HTTPS
- Use your DNS provider (e.g., Afraid DNS) to create A records pointing your domain to your EC2 instance's public IP.
- Use Traefik to enable HTTPS, leveraging Let's Encrypt for automatic certificate management.
- Update Traefik configuration in docker-compose.yml to include entrypoints for HTTPS and certificate resolvers.

## Access the Application
Frontend: https://your-domain.com
Backend API: https://your-domain.com/api
Adminer: https://db.your-domain.com

## Troubleshooting and Maintenance
Monitor logs for any issues with docker-compose logs.
Ensure all services are running correctly using docker-compose ps.
Regularly update your Docker images and containers for security and performance improvements.
