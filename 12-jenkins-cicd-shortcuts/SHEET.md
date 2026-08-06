# ⚙️ Module 12: Jenkins CI/CD Pipeline Commands & Examples

Quick-reference cheat-sheet for Jenkinsfile Declarative Pipeline syntax, Jenkins CLI triggers, Docker agent execution, and build debugging with practical examples.

---

## ⚡ 1. Declarative `Jenkinsfile` Syntax Example

```groovy
pipeline {
    agent any
    
    environment {
        APP_ENV = 'production'
        DOCKER_IMAGE = 'my-app:latest'
    }
    
    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/techindro/Penetration-testing-toolkit.git'
            }
        }
        
        stage('Build & Test') {
            steps {
                sh 'npm install'
                sh 'npm test'
            }
        }
        
        stage('Docker Build & Push') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
                // sh 'docker push $DOCKER_IMAGE'
            }
        }
    }
    
    post {
        always {
            cleanWs() // Clean workspace after completion
        }
        success {
            echo 'Build and Deployment Succeeded!'
        }
        failure {
            echo 'Build Failed! Please check pipeline logs.'
        }
    }
}
```

---

## 🛠️ 2. Jenkins CLI & Docker Execution Examples

```bash
# Example 1: Run Jenkins in Docker container quickly on localhost:8080
docker run -d -p 8080:8080 -p 50000:50000 --name jenkins_server -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts-jdk17
# Usage: Open http://localhost:8080 to access Jenkins Web UI dashboard.

# Example 2: Retrieve initial admin password from Jenkins container
docker exec jenkins_server cat /var/jenkins_home/secrets/initialAdminPassword
# Output: Returns 32-character initial administrator password string.

# Example 3: Trigger a Jenkins job build via HTTP API (Curl)
curl -X POST "http://jenkins_user:api_token@localhost:8080/job/MyPipeline/build"
# Usage: Triggers automated build from external webhooks or local terminal.
```
