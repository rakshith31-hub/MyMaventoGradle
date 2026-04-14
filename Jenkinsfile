pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Brijesh-ue/MyMavenToGradle.git'
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

        stage('Check Target Folder') {
            steps {
                sh 'ls -l target'
            }
        }

        stage('Run Application') {
            steps {
                sh 'java -jar target/MyMavenToGradle-1.0-SNAPSHOT.jar'
            }
        }

    }

    post {
        success {
            echo 'Build and execution successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
