# Django E-Commerce Application with DevOps Workflow

## **Overview**
This project is a proof-of-concept (PoC) implementation of an e-commerce application using the Django framework. The project follows DevOps principles to address issues faced by Ipswich Retail, such as slow deployment cycles, frequent downtime, and scalability challenges. 

Key features include:
- **Model-View-Template (MVT) Architecture** for modularity and scalability.
- **Continuous Integration and Deployment (CI/CD)** pipeline using GitHub Actions.
- **Containerization** using Docker for consistent environments.
- **Infrastructure as Code (IaC)** using Terraform for provisioning.
- **Monitoring and Logging** with Prometheus and Grafana.

---

## **Workflow**
This project employs a DevOps workflow designed for seamless development, testing, and deployment.

### **1. CI/CD Process**
- **Tool Used**: GitHub Actions.
- **Steps in the Pipeline**:
  1. Code is pushed to the repository.
  2. CI/CD workflow triggers automatically.
  3. Dependencies are installed.
  4. Unit tests are executed.
  5. Deployment logic is triggered upon successful tests.

Configuration file: [`.github/workflows/ci-cd.yml`](.github/workflows/ci-cd.yml)

### **2. Docker Setup**
- **Purpose**: Containerize the Django application for consistency across development, staging, and production environments.
- **Key Files**:
  - `Dockerfile`: Defines the image with the required dependencies.
  - `docker-compose.yml`: Allows for local orchestration and testing.
- **Commands**:
  - Build the Docker image:
    ```bash
    docker build -t django-ecommerce .
    ```
  - Run the container:
    ```bash
    docker run -p 8000:8000 django-ecommerce
    ```

### **3. Infrastructure Provisioning**
- **Tool Used**: Terraform.
- **Purpose**: Provision and manage cloud infrastructure as code.
- **Key Steps**:
  1. Define infrastructure in `main.tf`.
  2. Initialize Terraform:
     ```bash
     terraform init
     ```
  3. Apply configurations:
     ```bash
     terraform apply
     ```
- Example: AWS EC2 instance for deploying the application.

### **4. Monitoring Setup**
- **Tools Used**: Prometheus and Grafana.
- **Steps**:
  1. Prometheus collects metrics from the Django application.
  2. Grafana visualizes the metrics and sets up alerts.
  3. Example metrics:
     - HTTP request rates.
     - CPU and memory usage.
     - Application uptime.
- Configuration details can be found in the [`monitoring/README.md`](monitoring/README.md).

---

## **Getting Started**
Follow these steps to set up and run the project:

### **1. Prerequisites**
- Docker installed ([Download Docker](https://www.docker.com/products/docker-desktop)).
- Python 3.9 or higher installed.
- Git installed ([Download Git](https://git-scm.com/)).

### **2. Clone the Repository**
```bash
git clone https://github.com/your-username/Django-Ecommerce-DevOps.git
cd Django-Ecommerce-DevOps
```
### **3. Run the Application**
Without Docker
# Step 1: Set up a virtual environment (optional but recommended)
python -m venv env
source env/bin/activate  # For Linux/macOS
# or
env\Scripts\activate     # For Windows

# Step 2: Install dependencies
pip install -r requirements.txt

# Step 3: Apply database migrations
python manage.py migrate

# Step 4: Start the development server
python manage.py runserver

## With Docker
# Step 1: Build the Docker image
docker build -t django-ecommerce .

# Step 2: Run the Docker container
docker run -p 8000:8000 django-ecommerce

### 
Here’s the complete "Run the Application" section rewritten entirely in bash commands:

3. Run the Application
Without Docker
bash
Copy code
# Step 1: Set up a virtual environment (optional but recommended)
python -m venv env
source env/bin/activate  # For Linux/macOS
# or
env\Scripts\activate     # For Windows

# Step 2: Install dependencies
pip install -r requirements.txt

# Step 3: Apply database migrations
python manage.py migrate

# Step 4: Start the development server
python manage.py runserver
With Docker
bash
Copy code
# Step 1: Build the Docker image
docker build -t django-ecommerce .

# Step 2: Run the Docker container
docker run -p 8000:8000 django-ecommerce

### Access the Application
# Open your web browser and go to:
http://localhost:8000


### References
#Django Documentation
#Prometheus Documentation
#Grafana Documentation

