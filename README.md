<div align="center">

# 🐳 Dockerized Static Site

**A simple HTML page containerized with Docker and served via Nginx**

[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
[![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)](https://nginx.org/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)

</div>

---

## 📌 About This Project

This is a beginner-friendly DevOps project that walks through the full journey of taking a plain HTML file and deploying it as a containerized web application.

The workflow is simple:

```
Write HTML  →  Build Docker Image  →  Run Container  →  Serve with Nginx
```

No frameworks. No complex config. Just the fundamentals of containerization in action.

---

## 🧱 What's Inside

| File | Purpose |
|------|---------|
| `index.html` | The static webpage |
| `Dockerfile` | Instructions to build the Docker image |

---

## 🔄 How It Works

### 1️⃣ The HTML Page
A simple `index.html` file was written — the actual content of the website.

### 2️⃣ The Dockerfile
A `Dockerfile` was created to package that HTML file inside an **Nginx** container. Nginx acts as the web server that serves the HTML file when someone visits the site.

```dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
```

- `FROM nginx:alpine` — uses a lightweight Nginx base image
- `COPY` — places the HTML file where Nginx expects to serve it from

### 3️⃣ Build the Docker Image
The image was built using:

```bash
docker build -t dockerized-static-site .
```

### 4️⃣ Run the Container
The container was started and exposed on port `8080`:

```bash
docker run -d -p 8080:80 dockerized-static-site
```

The site is then accessible at `http://localhost:8080` — served by Nginx running inside the container.

---

## 💡 Key Concepts Covered

- ✅ Writing a basic `Dockerfile`
- ✅ Building a Docker image from scratch
- ✅ Running a Docker container
- ✅ Serving static content with Nginx
- ✅ Port mapping (`host:container`)

---

## 🛠 Prerequisites

- [Docker](https://docs.docker.com/get-docker/) installed on your machine

---

## ▶️ Run It Yourself

```bash
# Clone the repo
git clone https://github.com/SalvatoreOps/dockerized-static-site.git
cd dockerized-static-site

# Build the image
docker build -t dockerized-static-site .

# Run the container
docker run -d -p 8080:80 dockerized-static-site
```

Then open **http://localhost:8080** in your browser.

---
## ⚖️ License

```
MIT License

Copyright (c) 2026 SalvatoreOps

Permission is hereby granted, free of charge, to any person obtaining a copy
of this documentation and associated files, to deal in it without restriction,
including without limitation the rights to use, copy, modify, merge, publish,
and distribute, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the material.

THE MATERIAL IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND.
```

---

<div align="center">

Made by [SalvatoreOps](https://github.com/SalvatoreOps) · Learning DevOps one container at a time 🚀

</div>