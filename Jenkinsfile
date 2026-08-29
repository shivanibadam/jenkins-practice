pipeline {
    agent any
    environment {
	APP_NAME = 'jenkins-practice-app'
        ENVIRONMENT = 'dev'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building ${APP_NAME}"
		echo "Environment ${ENVIRONMENT}"
		sh 'cat Greetings.txt'
            }
        }

        stage('Test') {
            steps {
                echo 'Test stage started'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy stage started'
            }
        }
    }
}