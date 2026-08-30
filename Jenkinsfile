pipeline {
    agent any
	tools {
    		maven 'Maven-3'
		}
    parameters {
    choice(
        name: 'DEPLOY_ENV',
        choices: ['dev', 'qa', 'prod'],
        description: 'Choose deployment environment'
    )
}
    environment {
	APP_NAME = 'jenkins-practice-app'
        ENVIRONMENT = 'dev'
    }
    stages {
        stage('Build') {
            steps {
		sh 'mvn -version'
		sh 'mvn clean package'
                echo "Building ${APP_NAME}"
		echo "Deplyment Environment: ${params.DEPLOY_ENV}"
 		echo "Jenkins Build Number: ${BUILD_NUMBER}"
        	echo "Jenkins Job: ${JOB_NAME}"
		sh 'cat Greetings.txt'
		sh 'mkdir -p build'
		sh 'echo "Application Build ${BUILD_NUMBER}" > build/app.txt'
		archiveArtifacts artifacts: 'build/app.txt'
            }
        }
   	
   stage('Credentials Test') {
   	steps {
        	withCredentials([
    			usernamePassword(
        			credentialsId: 'shivani',
        			usernameVariable: 'TEST_USER',
        			passwordVariable: 'TEST_PASS'
    			)
		]) 
		{
    			sh 'echo "Username: $TEST_USER"'
    			echo "Password is available securely"
		}
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

post{
	always{
		cleanWs()
	}
	success{
		echo 'pipeline completed successfully'
	}
}
}