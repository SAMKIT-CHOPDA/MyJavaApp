pipeline {
    agent any

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
