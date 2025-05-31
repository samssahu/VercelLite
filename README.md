<img width="1559" alt="Screenshot 2024-07-14 at 6 18 46 PM" src="https://github.com/user-attachments/assets/28e843b2-73cf-437b-ac2a-0234b8249c84">

## VercelLite: (Personal Project)

**Description:**

VercelLite is a prototype for a serverless deployment platform inspired by Vercel. It allows users to deploy their applications by submitting a Git repository URL. The platform automatically builds the application in a Docker container, stores the build artifacts in AWS S3, and provides a custom domain mapping for public access. Users can also monitor the build logs in real-time through a socket connection.

**Tech Stack:**

* **Frontend:** nextjs
* **Backend:** Node.js (Express.js)
* **Containerization:** Docker
* **Cloud Storage:** AWS S3
* **Container Orchestration:** AWS ECS, ECR
* **Real-time Messaging:** Redis Pub/Sub
* **Real-time Communication:** Socket.IO 

**Workflow:**

1. **User submits Git repository URL:** The user provides the URL of their Git repository.
2. **Automatic build:** The platform clones the repository, builds the application using Docker containers within AWS ECS (or simpler Docker management), and stores the built artifacts in AWS S3.
3. **Custom domain mapping:** The user can configure a custom domain to be mapped to their deployed application. A reverse proxy is used to route requests from the custom domain to the application hosted in S3.
4. **Real-time build logs:** The platform uses Redis Pub/Sub to publish build logs in real-time. A client-side socket connection allows users to subscribe to these logs and monitor the build progress.

**Note:** This is a prototype and may not be production-ready. Further development is needed for features like user authentication, automated scaling, and advanced security measures.
