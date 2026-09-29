# AWS Cloud-Based E-Commerce Shopping Portal

A beginner-friendly **Python Flask e-commerce web application** created to practice AWS cloud deployment, database integration, and basic cloud operations.

## Project Overview

This project demonstrates how a Flask-based shopping portal can connect to AWS services for application hosting and data storage.

### Features
- Product listing page
- Product data retrieval from Amazon DynamoDB with local fallback data
- User registration
- MySQL database integration through Amazon RDS
- Contact and About pages
- Application health-check endpoint
- Gunicorn configuration for production deployment
- AWS Elastic Beanstalk configuration

## Technology Stack

- **Backend:** Python, Flask
- **Database:** Amazon DynamoDB, MySQL / Amazon RDS
- **AWS:** EC2-compatible deployment, DynamoDB, RDS, Elastic Beanstalk
- **Server:** Gunicorn
- **Frontend:** HTML, CSS

## Architecture

```text
User
  |
  v
Flask Web Application
  |
  +----> Amazon DynamoDB ----> Product Data
  |
  +----> Amazon RDS / MySQL --> User Registration
  |
  +----> /health -------------> Application Health Check
  |
  v
AWS Deployment (Elastic Beanstalk / EC2)
```

## Project Structure

```text
AWS-Cloud-Based-E-Commerce-Shopping-Portal/
├── application.py
├── requirements.txt
├── runtime.txt
├── Procfile
├── .ebextensions/
│   └── 01_environment.config
├── database/
│   ├── dynamodb.py
│   └── mysql_db.py
├── static/
│   └── css/
│       └── style.css
└── templates/
    ├── base.html
    ├── index.html
    ├── products.html
    ├── about.html
    ├── contact.html
    └── register.html
```

## Run Locally

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/AWS-Cloud-Based-E-Commerce-Shopping-Portal.git
cd AWS-Cloud-Based-E-Commerce-Shopping-Portal
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Windows:

```bash
.venv\Scripts\activate
```

Linux/macOS:

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Set the following variables when connecting to AWS resources:

```text
FLASK_SECRET_KEY=your-secret-key
AWS_REGION=ap-south-1
DYNAMODB_TABLE=shopping-products
MYSQL_HOST=your-rds-endpoint
MYSQL_USER=your-db-user
MYSQL_PASSWORD=your-db-password
MYSQL_DATABASE=shopping_portal
MYSQL_PORT=3306
```

**Never commit real AWS credentials, database passwords, `.env` files, or private keys to GitHub.**

### 5. Start the application

```bash
python application.py
```

Open:

```text
http://127.0.0.1:5000
```

## AWS Deployment

The repository includes a `Procfile` and `.ebextensions` configuration for deployment using **AWS Elastic Beanstalk**. AWS resources such as DynamoDB and RDS should be configured separately, with their connection details supplied through environment variables.

## Learning Outcomes

This project helped me practice:

- Flask application development
- AWS cloud deployment concepts
- DynamoDB integration using Boto3
- MySQL / RDS connectivity
- Environment-variable based configuration
- Gunicorn application serving
- Basic AWS Elastic Beanstalk deployment configuration
- Cloud application architecture

## Note

This is a **learning/fresher project** built to gain practical exposure to AWS and cloud-based application deployment. It is not intended to represent a production-scale e-commerce platform.

## Author

**Ajith B**  
Computer Science Engineering Graduate  
AWS & DevOps Learner
