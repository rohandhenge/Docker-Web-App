# 🐳 Containerized Web Application Deployment

## 📌 Project Overview

This project demonstrates how a Python Flask application can be packaged into a Docker image and executed inside a Docker container.

The goal is to understand the basic Docker workflow used in real-world application deployment.

## 🏗️ Architecture

Developer Code
      ↓
Dockerfile
      ↓
Docker Image
      ↓
Docker Container
      ↓
Web Browser


```
docker-web-app/
│
├── Dockerfile
├── app.py
├── requirements.txt
└── README.md

```

=================
📄 app.py
========================

from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return """
    <html>
        <head>
            <title>Docker Web App</title>
        </head>
        <body>
            <h1>Docker Deployment Successful 🚀</h1>
            <p>Hello from Rohan's Docker Container!</p>
            <p>Application is running successfully inside Docker.</p>
        </body>
    </html>
    """

app.run(host="0.0.0.0", port=5000)


=================
📄 requirements.txt
========================

Flask==3.1.2


=================
📄 Dockerfile
========================

FROM python:3.12-slim

WORKDIR /app

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY app.py .

EXPOSE 5000

CMD ["python", "app.py"]


=================
📄 README.md
========================


## 🛠️ Technologies Used

- Python
- Flask
- Docker
- Linux / WSL
- Git & GitHub

## 📂 Project Structure

```text
docker-web-app/
│
├── Dockerfile
├── app.py
├── requirements.txt
└── README.md
```




![](./img/final%20output.png)

![](./img/img%202.png)

![](./img/img%203.png)

![](./img/img%204.png)