pipeline {
    agent any
    tools {
        jdk 'jdk17'   // 👈 use the same name as in Jenkins Tools
        maven 'Maven-3.9.11' // optional if you defined Maven tool in Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                echo "Cloning Java project from GitHub..."
                git branch: 'main', url: 'https://github.com/SAMKIT-CHOPDA/MyJavaApp.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building project with Maven..."
                bat 'mvn clean package'
            }
        }

        stage('Run Application') {
            steps {
                echo "Running Java application..."
                bat 'java -jar target\\MyJavaApp-1.0-SNAPSHOT.jar'
            }
        }
    }

    post {
        success {
            echo " Build and Run Successful!"
        }
        failure {
            echo " Build or Run Failed!"
        }
    }
}
