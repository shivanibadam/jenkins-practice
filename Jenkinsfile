pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build stage started'
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