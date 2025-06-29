pipeline {
    agent any
    
    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }            

        stage('Restore Dependencies') {
            steps {
                sh 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                sh 'dotnet build --no-restore'
            }
        }

        stage('Test') {
            steps {
                sh 'dotnet test --no-build --framework net8.0'
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
        }
    }
}
