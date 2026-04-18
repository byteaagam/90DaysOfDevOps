# Week 6 : Jenkins ( CI/CD ) Basics and Advanced real world challenge

## Task 1: Create a Jenkins Pipeline Job for CI/CD

### 1. Set Up a Pipeline Job:
  - Create a new Pipeline job in Jenkins.
  - Write a basic Jenkinsfile that automates the build, test, and deployment of a sample application (e.g., a simple web app).
  - Suggested stages: Build, Test, Deploy.

<img width="512" height="768" alt="Screenshot (614)" src="https://github.com/user-attachments/assets/094fb766-a48d-42ff-b226-25764384bf14" />

### 2.Run and Verify the Pipeline
  - Trigger the pipeline and ensure each stage runs successfully.
  - Verify the execution by checking console logs and, if applicable, using docker ps to confirm container status.

<img width="512" height="189" alt="Screenshot (613)" src="https://github.com/user-attachments/assets/6acb1e6e-b2b3-4fdb-a076-679aa94a729d" />

### 3. Document in solution.md:
  - Include your Jenkinsfile code and explain the purpose of each stage.
  - Note any issues you encountered and how you resolved them.
   - Already Done

## Task 2: Configure and Scale Jenkins Agents/Nodes

### 1.Set Up Multiple Agents:
- Configure at least two agents (e.g., one Linux-based and one Windows-based) in Jenkins.
- Use Docker containers or VMs to simulate different environments.

<img width="512" height="382" alt="Screenshot (622)" src="https://github.com/user-attachments/assets/f2f07a26-7e9d-461b-92ef-9f3cecab509e" />

### 2.Label Agents:

- Assign labels (e.g., linux, windows) and modify your Jenkinsfile to run appropriate stages on the correct agent.

<img width="512" height="768" alt="Screenshot (621)" src="https://github.com/user-attachments/assets/113f2d2d-0c0c-4ea0-b0c0-c330895bd83c" />

### 3.Run Parallel Jobs:
- Create jobs that run in parallel across these agents.

<img width="512" height="768" alt="Screenshot (620)" src="https://github.com/user-attachments/assets/58031db9-d784-4fad-b5c0-cc486d4510b9" />

## Task 3: Push the Docker Image to DockerHub

### 1.Update the Docker Credentials on Jenkins

<img width="1129" height="826" alt="Gemini_Generated_Image_2hoz0q2hoz0q2hoz" src="https://github.com/user-attachments/assets/a5cc865c-34d0-403f-b09c-0b651d95a506" />

### 2.Add a new stage to pipeline 

<img width="512" height="245" alt="Screenshot (625)" src="https://github.com/user-attachments/assets/64b66957-5d1e-4769-9e65-88cbc6f36f59" />

### 3.Verify the push on DockerHub

<img width="1488" height="671" alt="Gemini_Generated_Image_2hoz0q2hoz0q2hoz (1)" src="https://github.com/user-attachments/assets/507b49a7-c0e6-4d69-9fb5-e5bfb3230756" />


## Task 4: Explain about github-Webhook

GitHub Webhooks let GitHub automatically notify Jenkins when an event (like a code push) happens, so Jenkins can trigger a build instantly (no polling needed).

**⚙️ Steps**

In Jenkins job → enable “GitHub hook trigger for GITScm polling”

Copy webhook URL:

http://<jenkins-url>/github-webhook/

In GitHub → Repo → Settings → Webhooks → Add:

Payload URL: above URL

Content type: application/json

Event: Push

Save → Push code → Jenkins triggers automatically 🚀

## Task 5 :Implement and Test RBAC in a Multi-Team Environment

### 1.Configure RBAC:

- Use Matrix-based security or the Role Strategy Plugin to create roles (e.g., Admin, Developer, Tester).
- Define permissions for each role.

  <img width="512" height="562" alt="Screenshot (629)" src="https://github.com/user-attachments/assets/6db04214-3250-40e6-9278-a400c548c80f" />

### 2. Create Test Accounts:
- Simulate real-world usage by creating user accounts for each role and verifying access.

<img width="512" height="768" alt="Screenshot (630)" src="https://github.com/user-attachments/assets/04c9bf16-c08b-4d09-abdf-f72ce90b11c1" />

## Task 6: Develop and Integrate a Jenkins Shared Library

### 1.Create a Shared Library Repository:
Set up a separate Git repository that hosts your shared library code.
Develop reusable functions (e.g., a function for sending notifications or a common test stage).

<img width="512" height="340" alt="Screenshot (635)" src="https://github.com/user-attachments/assets/7e351b5e-a6ea-455a-bf48-20fa99c52d78" />

### 2.Integrate the Library:
- Update your Jenkinsfile(s) from previous tasks to load and use the shared library.
- Use syntax similar to:

@Library('my-shared-library') _

pipeline {

    // pipeline code using shared functions
    
}

<img width="512" height="614" alt="Screenshot (636)" src="https://github.com/user-attachments/assets/f3aaba43-1d20-491b-ad18-dc4786b5d7e0" />

## Task 7: Troubleshooting, Monitoring & Advanced Debugging

### 1. Jenkins Agent Going Offline

**Issue:**

Jenkins agent frequently disconnects and goes offline.

**Cause:**

- Low disk space
- Agent process crashing
- Network instability

**Solution:**

Free disk space:

- docker system prune -a -f
- rm -rf /home/ubuntu/jenkins/workspace/*

**Restart agent:**

- sudo systemctl restart jenkins
- Run agent as a service for auto-restart.

### 2. Disk Space Full (EC2)

**Issue:**

Disk usage reaching ~85–100%

**Cause:**

- Docker images & containers
- Jenkins build artifacts
- Logs and cache files

**Solution:**

- Clean Docker:

docker system prune -a -f

docker volume prune -f

- Remove old builds:

rm -rf /var/lib/jenkins/jobs/*/builds/*

### 3. Permission Denied Errors

**Issue:**

Jenkins unable to access workspace or files

**Cause:**

Incorrect file ownership or permissions

**Solution:**

sudo chown -R ubuntu:ubuntu /home/ubuntu/jenkins

sudo chmod -R 755 /home/ubuntu/jenkins

## Task 8: Integrate Email Notifications for Build Events

### ⚙️ Configuration Steps

**1. Install Required Plugin**

Go to Manage Jenkins → Manage Plugins

Install: Email Extension Plugin

**2. Configure SMTP Settings**

Navigate to: Manage Jenkins → Configure System

Scroll to Extended E-mail Notification

**🧪 Pipeline Configuration**

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building project...'
            }
        }
    }

    post {
        success {
            emailext (
                subject: "SUCCESS: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "Build succeeded.\nCheck details: ${env.BUILD_URL}",
                to: "your-email@gmail.com"
            )
        }
        failure {
            emailext (
                subject: "FAILED: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "Build failed.\nCheck details: ${env.BUILD_URL}",
                to: "your-email@gmail.com"
            )
        }
    }
}
