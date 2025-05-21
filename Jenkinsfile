pipeline {
    agent any

    tools {
        maven 'Maven_3.9.9' // Define in Jenkins tools config
        jdk 'JDK_21'        // Define in Jenkins tools config
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Rohit-Mane5857/makemytrip.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
