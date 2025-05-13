# exp8docker
Great! Let's build a **simple Python Flask app**, then **containerize it using Docker**. I’ll walk you through it **step-by-step and clearly**.

---

## 🚀 Goal

We’ll create a small **Flask web app** that shows “Hello from Flask in Docker!”, and then run it inside a Docker container.

---

## ✅ Step 1: Create Project Folder

Open terminal (Command Prompt, VSCode Terminal, etc.) and run:

```bash
mkdir flask-docker-app
cd flask-docker-app
```

---

## ✅ Step 2: Create Flask App

Create a file named `app.py`:

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return 'Hello from Flask in Docker!'

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)
```

---

## ✅ Step 3: Create Requirements File

Create a file named `requirements.txt`:

```
flask
```

This tells Docker to install Flask.

---

## ✅ Step 4: Create Dockerfile

Create a file named `Dockerfile` **(no extension)**:

```Dockerfile
# Use official Python image
FROM python:3.9

# Set working directory in container
WORKDIR /app

# Copy files into container
COPY . .

# Install dependencies
RUN pip install -r requirements.txt

# Expose Flask port
EXPOSE 5000

# Run the Flask app
CMD ["python", "app.py"]
```

---

## ✅ Step 5: Build Docker Image

Run this in terminal:

```bash
docker build -t flask-docker-app .
```

This builds the image and names it `flask-docker-app`.

---

## ✅ Step 6: Run Docker Container

Now run the app:

```bash
docker run -p 5000:5000 flask-docker-app
```

Your Flask app is now running inside Docker.

---

## ✅ Step 7: Open in Browser

Go to your browser and open:

```
http://localhost:5000
```

You should see:

```
Hello from Flask in Docker!
```

---

## ✅ Step 8: Stop the Container

Press `Ctrl + C` in the terminal to stop.

You can also stop all containers by:

```bash
docker ps       # See running containers
docker stop <container_id>
```

---

## 🔁 Optional Add-ons

* Add HTML templates using `Flask + Jinja2`
* Add a form and input
* Connect to a database
* Push your Docker image to **Docker Hub**

---

Would you like me to:

* Add a login form?
* Show how to use environment variables?
* Connect this to Jenkins or GitHub Actions for DevOps?

Let me know — happy to help!
