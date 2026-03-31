# mini-project-gcloudrun-hello

# Cloud Run Hello World 🌐

A simple Node.js "Hello World" application deployed on **Google Cloud Run**.  
This project demonstrates containerization with Docker, build automation using **Cloud Build**, and deployment via **Artifact Registry**.

---

## 🚀 Project Overview
- **Language:** Node.js (Express)
- **Containerization:** Docker
- **Build Tool:** Google Cloud Build
- **Registry:** Artifact Registry
- **Deployment:** Cloud Run (fully managed, serverless)

---

## 📂 Files
- `appgcloud.js` → Express app serving "Hello World"
- `package.json` → Dependencies and start script
- `Dockerfile` → Instructions to build the container

---

## ⚙️ Setup & Deployment

### 1. Clone the Repo
```bash
git clone https://github.com/leenatacswamyrao/mini-project-gcloudrun-hello.git
cd cloudrun-hello
```

### 2. Create Artifact Registry Repo (first time only)
```bash
gcloud artifacts repositories create cloudrun-repo \
  --repository-format=docker \
  --location=asia-south1 \
  --description="Docker repo for Cloud Run"
```

### 3. Build the Image
```bash
gcloud builds submit \
  --tag asia-south1-docker.pkg.dev/cloudrun-hello-491911/cloudrun-repo/cloudrun-hello
```

### 4. Deploy to Cloud Run
```bash
gcloud run deploy cloudrun-hello \
  --image asia-south1-docker.pkg.dev/cloudrun-hello-491911/cloudrun-repo/cloudrun-hello \
  --platform managed \
  --region asia-south1 \
  --allow-unauthenticated
```

---

## ✅ Result
After deployment, Cloud Run provides a **public HTTPS URL**.  
Open it in your browser → you’ll see: https://cloudrun-hello-487562171487.asia-south1.run.app/

```
Hello World from Cloud Run!
```

---

## 📌 Notes
- Region `asia-south1` is Mumbai (closest to Pune).  
- `--allow-unauthenticated` makes the service publicly accessible.  

---

## 🎯 Why This Project Matters
This repo shows:
- Hands-on experience with **cloud-native deployment**.  
- Ability to manage **APIs, billing, and quotas** efficiently.  


Would you like me to also draft a **short “resume-ready bullet point”** you can paste into your CV/LinkedIn, highlighting this Cloud Run project as proof of your cloud-native skills?
