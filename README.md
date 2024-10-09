# My web Application
This project demonstrates the development of a web application using a Python backend, HTML/JavaScript frontend, and database connectivity. The application is deployed using Docker containers and Kubernetes. GitHub is used for version control, branching, and collaboration.

The application features:
A Frontend with a form (built using HTML, CSS, and JavaScript) to capture user input.
A Backend (written in Python) that processes the data and connects to a database for storage.
Docker containers for both the frontend and backend.
Deployment on a Kubernetes cluster (Google Kubernetes Engine).
Architecture Overview
Frontend: A static webpage created with HTML, CSS, and JavaScript that collects two input values.
Backend: A Python application using Flask that handles form submissions and stores the data in a database (hosted on Google Cloud SQL).
Database: Google Cloud SQL with PostgreSQL or SQL Server as the relational database.
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
Database: PostgreSQL or SQL Server (Hosted on Google Cloud SQL)
Version Control: GitHub
Containerization: Docker
Orchestration: Kubernetes (GKE - Google Kubernetes Engine)
Project Structure
bash
Copy code
WebApp-Docker-K8s/
│
├── frontend/               # Frontend files
│   ├── index.html          # Main HTML file
│   ├── style.css           # CSS for responsive styling
│   └── app.js              # JavaScript for form validation
│
├── backend/                # Backend application
│   └── app.py              # Python Flask app to handle API requests
│
├── database/               # Database configurations (optional SQL files)
│   └── init.sql            # SQL script to create necessary tables
│
├── Dockerfile.frontend      # Dockerfile for frontend container
├── Dockerfile.backend       # Dockerfile for backend container
│
├── k8s-deployment/          # Kubernetes YAML configurations
│   ├── frontend.yaml        # Kubernetes configuration for frontend service
│   └── backend.yaml         # Kubernetes configuration for backend service
│
├── README.md                # Project documentation (this file)
└── .gitignore               # Git ignore file
Setup Instructions
Prerequisites
Before running this project, make sure you have the following installed:

Git
Docker
Kubernetes CLI
Google Cloud SDK
Python 3.x
1. Clone the Repository
bash
Copy code
git clone https://github.com/yourusername/WebApp-Docker-K8s.git
cd WebApp-Docker-K8s
2. Setup Database (Google Cloud SQL)
Configure a PostgreSQL or SQL Server instance on Google Cloud.
Create the necessary table using init.sql.
3. Set Environment Variables
bash
Copy code
export SQLSERVER_IP="your_sql_instance_ip"
export SQLSERVER_DB="your_database_name"
export SQLSERVER_USER="your_database_user"
export SQLSERVER_PASS="your_database_password"
4. Run the Application Locally
Backend
bash
Copy code
cd backend
pip install -r requirements.txt
python app.py
Frontend
Navigate to http://localhost:5000 to view the application.

Usage
Frontend
The frontend provides a form where users can submit two values.
The form is validated using JavaScript, and the submitted data is sent to the backend.
Backend
The backend processes the submitted data and inserts it into the connected SQL database.
Docker Containerization
1. Build Docker Images
Frontend:
bash
Copy code
docker build -t frontend-app -f Dockerfile.frontend .
Backend:
bash
Copy code
docker build -t backend-app -f Dockerfile.backend .
2. Run Docker Containers
bash
Copy code
docker run -d -p 80:80 frontend-app
docker run -d -p 5000:5000 backend-app
Kubernetes Deployment
1. Create Kubernetes Cluster on GKE
bash
Copy code
gcloud container clusters create webapp-cluster --num-nodes=3
gcloud container clusters get-credentials webapp-cluster
2. Apply Kubernetes Configurations
bash
Copy code
kubectl apply -f k8s-deployment/frontend.yaml
kubectl apply -f k8s-deployment/backend.yaml
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
