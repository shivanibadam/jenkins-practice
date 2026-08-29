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
 		echo "Jenkins Build Number: ${BUILD_NUMBER}"
        	echo "Jenkins Job: ${JOB_NAME}"
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