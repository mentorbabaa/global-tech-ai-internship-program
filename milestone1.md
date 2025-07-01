# Task Tracker with CI/CD Pipeline

This is a simple Flask-based Task Tracker application containerized with Docker and CI/CD enabled using Jenkins.

---

## 📌 Project Breakdown

### ✅ Task 1: App Development
- Develop a basic Flask app with REST APIs
- Add, update, and delete tasks (in-memory)
- Test locally using `curl` or Postman

### ✅ Task 2: GitHub Collaboration
- Push the project to GitHub
- Create a clear `README.md` for contributors
- Open to Pull Requests and version control best practices

### ✅ Task 3: CI/CD with Jenkins & Docker
- Containerize the application
- Create a Jenkins pipeline
- Deploy on Docker via Jenkins automation

---

## 🧾 Features
- Add, update, and delete tasks
- Store tasks in-memory (for simplicity)
- Flask RESTful API
- Jenkins integration for CI/CD

---

## 🗂 Project Structure
```
.
├── app.py
├── requirements.txt
├── Dockerfile
├── jenkinsfile
└── README.md
```

---

## ▶️ How to Run (Locally)

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/task-tracker-devops.git
cd task-tracker-devops
```

### 2. Create a Virtual Environment (Optional)
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the Flask App
```bash
python app.py
```

Open your browser and go to: `http://localhost:5000`

---

## 🐳 Docker Setup

### 1. Build Docker Image
```bash
docker build -t task-tracker .
```

### 2. Run Docker Container
```bash
docker run -d -p 5000:5000 task-tracker
```

---

## 🤖 Jenkins CI/CD Setup

### 1. Create `jenkinsfile` in root

```groovy
pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        echo 'Building...'
        sh 'docker build -t task-tracker .'
      }
    }

    stage('Test') {
      steps {
        echo 'Running tests...'
        sh 'echo "No tests defined"'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying...'
        sh 'docker run -d -p 5000:5000 task-tracker'
      }
    }
  }
}
```

### 2. Connect Jenkins to GitHub
- Create a new Jenkins job (Pipeline)
- Link to your GitHub repo
- Paste this `jenkinsfile` in Pipeline config

---

## 🧪 API Endpoints
- `GET /tasks` - List all tasks
- `POST /tasks` - Add a task `{ "task": "My Task" }`
- `DELETE /tasks/<id>` - Delete task by ID

---

## 🔧 Source Code

### `app.py`
```python
from flask import Flask, request, jsonify

app = Flask(__name__)
tasks = []

@app.route('/')
def home():
    return "Welcome to the Task Tracker!"

@app.route('/tasks', methods=['GET'])
def get_tasks():
    return jsonify(tasks)

@app.route('/tasks', methods=['POST'])
def add_task():
    data = request.get_json()
    task = {"id": len(tasks) + 1, "task": data['task']}
    tasks.append(task)
    return jsonify(task), 201

@app.route('/tasks/<int:task_id>', methods=['DELETE'])
def delete_task(task_id):
    global tasks
    tasks = [t for t in tasks if t['id'] != task_id]
    return '', 204

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)
```

### `requirements.txt`
```
flask
```

### `Dockerfile`
```Dockerfile
FROM python:3.9
WORKDIR /app
COPY requirements.txt ./
RUN pip install -r requirements.txt
COPY . .
CMD ["python", "app.py"]
```

---

## 📫 License
This project is open-source under MIT.
