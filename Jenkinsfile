pipeline {
    agent any

    tools {
        maven 'Maven 3.8.5'   // Replace with your configured Maven name
        jdk 'JDK11'           // Replace with your configured JDK name
    }

    environment {
        GIT_REPO = 'https://github.com/AKSHADA-TECH-PIXEL/jenkinproject.git'
    }

    stages {
        stage('Clone Repo') {
            steps {
                git url: "${env.GIT_REPO}", branch: 'main'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }

    post {
        success {
            echo '✅ Maven build successful.'
        }
        failure {
            echo '❌ Maven build failed.'
        }
    }
}

