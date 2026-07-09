# Student Registration System and Jenkins CI/CD Pipeline for Flask Application

A simple **Flask** web application to manage student records with **MongoDB** as the backend database. Users can **add, view, update, and delete** student details.

---

## Features

* List all students on the home page
* Add a new student
* Update existing student details
* Delete a student with confirmation
* Simple and responsive UI using Bootstrap

---

## Tech Stack

* **Backend:** Python, Flask
* **Database:** MongoDB (via Flask-PyMongo)
* **Frontend:** HTML, Jinja2 templates, Bootstrap 5
* **Environment Variables:** Managed via `.env` file

---

## Setup Instructions

### 1. Clone the repository

```bash
git clone <your-repo-url>
cd <repo-folder>
```

### 2. Create and activate a virtual environment

```bash
python -m venv venv
# Activate venv
# Windows:
venv\Scripts\activate
# Linux / Mac:
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

**`requirements.txt` example:**

```
Flask
Flask-PyMongo
python-dotenv
bson
```

### 4. Configure environment variables

Create a `.env` file in the project root:

```
MONGO_URI=<your-mongodb-connection-string>
SECRET_KEY=<your-secret-key>
```

### 5. Run the application

```bash
python app.py
```

Open your browser at: [http://localhost:8000](http://localhost:8000)

---

## Project Structure

```
project/
│
├── templates/
│   ├── base.html
│   ├── index.html
│   ├── add_student.html
│   ├── update_student.html
│
├── app.py
├── requirements.txt
└── .env
```

---

## Screenshots

**Home Page**
Lists all students with Edit/Delete buttons.
- <img width="1902" height="607" alt="image" src="https://github.com/user-attachments/assets/a58a6a6d-4978-4769-8074-232e4d31e69d" />


**Add Student**
Form to add a new student.
- <img width="1897" height="801" alt="image" src="https://github.com/user-attachments/assets/d65d25c3-ebb5-410a-adb1-e130ad7c5878" />


**Update Student**
Form pre-filled with student details.
- <img width="1905" height="897" alt="image" src="https://github.com/user-attachments/assets/04febf01-879f-431f-ab07-abcfb993acf1" />

# Jenkins CI/CD Pipeline for Flask Application

## Project Overview

This project demonstrates the implementation of a Continuous Integration and Continuous Deployment (CI/CD) pipeline using **Jenkins** for a simple **Python Flask** web application.

The pipeline automatically performs the following tasks:

- Clone the source code from GitHub.
- Create a Python Virtual Environment.
- Install all required Python dependencies.
- Execute unit tests using **pytest**.
- Deploy the Flask application if all tests pass successfully.

This project was developed as part of the **Hero Vired DevOps Assignment**.

---

# Project Architecture

```
Developer
     │
     ▼
GitHub Repository
     │
     ▼
Jenkins Pipeline
     │
     ├── Checkout Source Code
     ├── Install Dependencies
     ├── Run Unit Tests
     ├── Deploy Flask Application
     ▼
Running Flask Application
```

---

# Project Structure

```
flask-cicd-project/
│
├── app.py
├── test_app.py
├── requirements.txt
├── Jenkinsfile
├── README.md
└── .gitignore
```

---

# Technologies Used

- Python 3.12
- Flask
- Pytest
- Jenkins
- Docker
- Git
- GitHub
- Ubuntu 24.04 LTS
- AWS EC2

---

# Prerequisites

Before running this project, make sure the following software is installed:

- Ubuntu 24.04 LTS
- Python 3
- pip
- Git
- Docker
- Jenkins
- GitHub Account

---

# Setup Instructions

## Step 1: Clone Repository

```bash
git clone https://github.com/<your-username>/flask-cicd-project.git

cd flask-cicd-project
```

---

## Step 2: Create Virtual Environment

```bash
python3 -m venv venv
```

---

## Step 3: Activate Virtual Environment

Linux

```bash
source venv/bin/activate
```

Windows

```cmd
venv\Scripts\activate
```

---

## Step 4: Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Step 5: Run Flask Application

```bash
python app.py
```

Open browser

```
http://localhost:5000
```

---

## Step 6: Run Unit Tests

```bash
pytest
```

Expected Output

```
====================
1 passed
====================
```

---

# Jenkins Pipeline

The project contains a **Declarative Jenkins Pipeline** inside the `Jenkinsfile`.

The pipeline contains four stages.

## Stage 1 – Checkout

Downloads the latest source code from GitHub.

## Stage 2 – Build

Creates a Python virtual environment and installs all required dependencies using `pip`.

## Stage 3 – Test

Runs the unit tests using **pytest**.

If any test fails, the pipeline stops.

## Stage 4 – Deploy

Starts the Flask application.

---

# Pipeline Workflow

```
Checkout
      │
      ▼
Build
      │
      ▼
Install Dependencies
      │
      ▼
Run Tests
      │
      ▼
Deploy Flask App
```

---

# Jenkinsfile

The Jenkinsfile performs the following tasks:

- Clone Repository
- Install Dependencies
- Execute Tests
- Deploy Flask Application
- Display Success or Failure Messages

---

# Running Jenkins

Start Jenkins and open

```
http://<EC2-Public-IP>:8080
```

Example

```
http://13.xxx.xxx.xxx:8080
```

---

# Build Commands

### Build

```bash
pip install -r requirements.txt
```

### Test

```bash
pytest
```

### Deploy

```bash
python app.py
```

---

# Expected Jenkins Pipeline Output

```
Pipeline Started

↓

Checkout Successful

↓

Dependencies Installed

↓

Tests Passed

↓

Application Deployed Successfully

↓

Pipeline Completed Successfully
```

---

# Sample Application Output

Home Page

```
Hello from Jenkins CI/CD Pipeline!
```

---

# Future Improvements

- GitHub Webhooks
- Email Notifications
- Docker Image Creation
- Kubernetes Deployment
- SonarQube Integration
- Slack Notifications
- AWS EC2 Automatic Deployment

---
## Screenshots

**pipeline is successfull**
Lists all students with Edit/Delete buttons.
<img width="1319" height="650" alt="Screenshot 2026-07-09 132158" src="https://github.com/user-attachments/assets/ced5c07f-f11b-4130-9095-47b223c8785f" />



**Jenkins pipeline**
<img width="1216" height="658" alt="Screenshot 2026-07-09 133320" src="https://github.com/user-attachments/assets/482de418-7e03-4744-8bce-f06200c311c0" />



**jenkins is ready**
<img width="1322" height="487" alt="Screenshot 2026-07-02 235020" src="https://github.com/user-attachments/assets/0519dd4b-50ef-4c09-af3f-78a411e242e5" />


# License

This project is developed for educational purposes as part of the Hero Vired DevOps Assignment.


---

## Notes

* Make sure MongoDB is running and accessible via the URI in `.env`
* Delete action includes a confirmation page to prevent accidental deletion
* Uses `ObjectId` from `bson` to work with MongoDB document IDs
* If you use MongoDB Atlas on macOS, install dependencies again (`pip install -r requirements.txt`). This project now uses `certifi` CA bundle explicitly to avoid common TLS certificate verification failures with `pymongo`.

---

## License

MIT License

---



