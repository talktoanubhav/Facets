pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                dotnet build  sample.txt
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
