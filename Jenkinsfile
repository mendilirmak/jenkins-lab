pipeline {
    agent any

    environment {
        APP_VERSION = '1.0'
        APP_NAME    = 'MyApp'
        DOCKER_REPO = 'MyDockerRepo'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Build'
                sh 'echo "This is build stage" > app.txt'
                sh 'echo $APP_NAME $APP_VERSION $DOCKER_REPO'
            }
        }
        stage('Test') {
            steps {
                echo 'Test'
                sh 'ls app.txt'
                sh 'echo "Pipeline Name: $JOB_NAME, Build Number: $BUILD_NUMBER"'

            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy'
                sh 'mkdir -p deploy && mv app.txt deploy'
                
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
