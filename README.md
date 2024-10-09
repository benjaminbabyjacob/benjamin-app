# My web Application
This project demonstrates the development of a web application using a Python backend, HTML/JavaScript frontend, and database connectivity. The application is deployed using Docker containers and Kubernetes. GitHub is used for version control, branching, and collaboration.

The application features:
A Frontend with a form to capture user input.
A Backend (written in Python) that processes the data and connects to a database for storage.
Docker containers for both the frontend and backend.
Deployment on a Kubernetes cluster (Google Kubernetes Engine).

Architecture Overview
Frontend: A static webpage created that collects two input values.
Backend: A Python application using Flask that handles form submissions and stores the data in a database (hosted on Google Cloud SQL).
Database: Google Cloud SQL with SQL Server as the relational database.
Containerization: Both frontend and backend are containerized using Docker.
Kubernetes: Kubernetes is used to orchestrate the deployment of the application with proper service management using YAML files.

Features
Form submission with data validation on the frontend.
Data insertion into a SQL database using a Python backend.
Version control using GitHub with branches and pull requests.
Containerization using Docker.
Deployment on Kubernetes using YAML configuration files.

Technologies Used
Frontend: HTML, CSS, JavaScript
Backend: Python (Flask)
Database: SQL Server (Hosted on Google Cloud SQL)
Version Control: GitHub
Containerization: Docker
Orchestration: Kubernetes

Usage
Frontend
The frontend provides a form where users can submit two values.
The form is validated using JavaScript, and the submitted data is sent to the backend.
Backend
The backend processes the submitted data and inserts it into the connected SQL database.

Docker Containerization
1. Build Docker Images
2. Run Docker Containers

Kubernetes Deployment
1. Create Kubernetes Cluster on GKE
2. Apply Kubernetes Configurations
3. Access the Application
Once deployed, access the application via the Load Balancer created by Kubernetes.

Version Control
This project uses GitHub for version control with the following practices:
Branching: New features and bug fixes are developed in separate branches.
Pull Requests: All changes are reviewed via pull requests before merging.
Commit Messages: Meaningful commit messages are used to document changes.

Challenges Faced
Database Connectivity: Managing secure connections between the application and Google Cloud SQL required setting up correct credentials and networking permissions.
Kubernetes Configuration: Writing optimized YAML files for Kubernetes deployments and configuring load balancers was a learning experience.
Docker Optimization: Reducing image size by optimizing Dockerfiles and understanding multi-stage builds.
