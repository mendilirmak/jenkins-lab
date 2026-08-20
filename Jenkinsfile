pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'echo "This is build stage" > app.txt'
                echo 'Build'
            }
        }
        stage('Test') {
            steps {
                sh 'ls app.txt'
                echo 'Test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'mkdir -p deploy && mv app.txt deploy'
                echo 'Deploy'
            }
        }
    }

    post {
        always {
            echo 'Delete Workspace'
            deleteDir()
        }
    }
}
