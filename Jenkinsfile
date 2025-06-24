pipeline {
    agent any

    stages {
        stage('Checkout the repository') {
            steps {
                checkout scm
            }
        }

        stage('Restore the project') {
            steps {
                sh 'dotnet restore'
            }
        }


        stage('Build the project') {
            steps {
                sh 'dotnet build'
            }
        }

        stage('Run tests') {
            steps {
                sh 'dotnet test'
            }
        }
    }
    post {
        always {
            echo 'Pipeline completed'
        }
        success {
            echo 'Build succeeded'
        }
        failure {
            echo 'Build failed'
        }
    }
}