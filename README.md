# sit737-2025-prac5d
# SIT737 - 2025 - Practical 5.2D  
## Dockerization - Publishing the Microservice into the Cloud

---

## Overview  
In this task, the goal is to publish the existing microservice (developed in Task 5.1P) to the cloud using Docker and Google Cloud Platform (GCP). This involves containerizing the microservice and pushing the Docker image to a private container registry hosted on GCP.

---

## Tools Used  
- GitHub  
- Visual Studio Code  
- Node.js  
- Docker  
- Google Cloud SDK

---

## Step-by-Step Process  

### 1. Clone the New GitHub Repository  
```bash
git clone https://github.com/KT-277/sit737-2025-prac5d
cd sit737-2025-prac5d
```

### 2. Copy the Files from Previous Project  
Manually copy all files (including `Dockerfile`, `app.js`, `package.json`, etc.) from your previous repository (5.1P) into this new one. Alternatively, if both repos are on your system:

```bash
cp -r ../sit737-2025-prac5p/* .
```

### 3. Push the Files to GitHub  
```bash
git add .
git commit -m "Initial commit for 5.2D - Dockerized microservice and pushed to GCP"
git push -u origin main
```

---

## Dockerization and Cloud Publishing  

### 4. Authenticate Docker to Use Google Container Registry  
```bash
gcloud auth configure-docker
```

### 5. Tag the Docker Image  
Replace `YOUR_PROJECT_ID` with your actual Google Cloud project ID.  
```
docker tag microservice-image gcr.io/PROJECT_ID/microservice-image
```

### 6. Push the Docker Image to Google Cloud  
```
docker push gcr.io/PROJECT_ID/microservice-image
```

### 7. Verify by Pulling and Running the Image  
```
docker pull gcr.io/PROJECT_ID/microservice-image
docker run -p 3000:3000 gcr.io/PROJECT_ID/microservice-image
```

---

## Outcome  
- The microservice is now successfully containerized using Docker.  
- It has been published to a private container registry on Google Cloud.  
- You can now run your service from anywhere by pulling the image from the registry.
