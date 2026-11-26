
pipeline {
    agent any

    tools {
        nodejs 'NodeJS-22'
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out Rick and Morty project'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Rick and Morty application'
                sh 'node --version'
                sh 'npm --version'
                sh 'npm ci'
                sh 'npm run build'
            }
        }

        stage('Docker Build') {
            steps {
                echo 'Building Docker image'
                sh 'docker build -t rick-morty-app:2.0.0 .'
            }
        }

        stage('Success') {
            steps {
                echo 'Rick and Morty application built successfully!'
            }
        }
    }
}
