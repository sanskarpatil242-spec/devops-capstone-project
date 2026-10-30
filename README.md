# IBM DevOps Capstone Project - Customer Accounts Microservice

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Python 3.9](https://img.shields.io/badge/Python-3.9-green.svg)](https://shields.io/)
[![CI build](https://github.com/sanskarpatil242-spec/devops-capstone-project/actions/workflows/ci-build.yaml/badge.svg)](https://github.com/sanskarpatil242-spec/devops-capstone-project/actions/workflows/ci-build.yaml)

This repository contains the complete implementation for the **Customer Accounts Microservice** capstone project as part of the **IBM DevOps and Software Engineering Professional Certificate**.

---

## Project Overview

The objective of this project is to implement a robust, production-ready, RESTful **Customer Accounts Microservice** for an e-commerce platform following modern Agile and DevOps practices:
- **Agile Planning & Kanban**: User stories defined using Mike Cohn's template with BDD Gherkin acceptance criteria, tracked on GitHub Projects.
- **RESTful API Architecture**: Implementation of full CRUD operations (`POST /accounts`, `GET /accounts`, `GET /accounts/{id}`, `PUT /accounts/{id}`, `DELETE /accounts/{id}`).
- **Test-Driven Development (TDD)**: Comprehensive automated test suite using `nosetests` with over 95% test coverage.
- **Application Security & CORS**: Secure headers enforced via `Flask-Talisman` and Cross-Origin Resource Sharing enabled via `Flask-CORS`.
- **Continuous Integration (CI)**: GitHub Actions workflow (`ci-build.yaml`) automating linting with `flake8` and test execution with `nosetests` on every push and pull request.
- **Containerization**: Secure, lightweight container image created with Dockerfile running as non-root user `theia`.
- **Kubernetes Deployment**: Declarative Kubernetes manifests for deployment, services, and horizontal pod replication.
- **Continuous Delivery (CD)**: Automated deployment pipeline using Tekton pipelines.

---

## API Endpoints

| Method | Endpoint | Description | Status Code |
|---|---|---|---|
| `GET` | `/` | Root URL providing service metadata | `200 OK` |
| `GET` | `/health` | Health check endpoint | `200 OK` |
| `POST` | `/accounts` | Create a new customer account | `201 Created` |
| `GET` | `/accounts` | List all customer accounts | `200 OK` |
| `GET` | `/accounts/<id>` | Read a specific customer account by ID | `200 OK` / `404 Not Found` |
| `PUT` | `/accounts/<id>` | Update an existing customer account by ID | `200 OK` / `404 Not Found` |
| `DELETE` | `/accounts/<id>` | Delete a customer account by ID | `204 No Content` |

---

## Running the Service Locally

### Prerequisites
- Python 3.9
- PostgreSQL (or SQLite for development)

### Setup & Run
```bash
# Clone the repository
git clone https://github.com/sanskarpatil242-spec/devops-capstone-project.git
cd devops-capstone-project

# Install dependencies
pip install -r requirements.txt

# Run linting
flake8 . --count --max-complexity=10 --max-line-length=127 --statistics

# Run automated tests
nosetests -v --with-coverage --cover-package=service

# Run the Flask service
honcho start
```

---

## Author
- **GitHub**: [sanskarpatil242-spec](https://github.com/sanskarpatil242-spec)
- **Repository**: [devops-capstone-project](https://github.com/sanskarpatil242-spec/devops-capstone-project)
