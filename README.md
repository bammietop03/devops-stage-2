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

## Running the Application with Docker
To run the entire application using Docker, follow these steps:

Prerequisites

Make sure you have Docker and Docker Compose installed on your machine. You can download and install Docker and Docker Compose

#### Clone the Repository
First, clone this repository to your local machine:

    git clone https://github.com/yourusername/fullstack-fastapi-react-template.git
    cd fullstack-fastapi-react-template

#### Build and Run the Docker Containers
Run the following command to build and start the Docker containers:

    docker-compose up --build
This command will build the Docker images for the frontend and backend services, and then start the containers.

#### Access the Application
Once the containers are up and running, you can access the application via the following URLs:

Frontend: http://localhost (assuming you have configured your Nginx Proxy Manager to route home.detprod.com to the frontend container)

Backend:
API: http://localhost/api
API Documentation (Swagger UI): http://localhost/docs
API Documentation (ReDoc): http://localhost/redoc

Adminer: http://db.detprod.com:8080 (for database management)

#### Stopping the Application
To stop the Docker containers, press Ctrl+C in the terminal where docker-compose up is running, or run the following command in another terminal

    docker-compose down
This command will stop and remove the containers defined in the docker-compose.yml file.

## Additional Configuration
#### Nginx Proxy Manager

Ensure that you have configured the Nginx Proxy Manager to route traffic correctly:

Access Nginx Proxy Manager: Navigate to the Nginx Proxy Manager UI.

Add Proxy Hosts:
#### Frontend:

    Domain Names: home.detprod.com
    Scheme: http
    Forward Hostname/IP: frontend
    Forward Port: 80
    Enable Websockets Support.
    Enable SSL and configure Let's Encrypt.

#### Backend:

    Domain Names: home.detprod.com
    Scheme: http
    Forward Hostname/IP: backend
    Forward Port: 8000
    Enable Websockets Support.
    Enable SSL and configure Let's Encrypt.
Configure custom locations for /api, /docs, and /redoc to forward to the backend service.

#### Adminer:

    Domain Names: db.detprod.com
    Scheme: http
    Forward Hostname/IP: adminer
    Forward Port: 8080
    Enable SSL and configure Let's Encrypt.

#### Nginx Proxy Manager:

    Domain Names: proxy.detprod.com
    Scheme: http
    Forward Hostname/IP: proxy_manager
    Forward Port: 81
    Enable SSL and configure Let's Encrypt.