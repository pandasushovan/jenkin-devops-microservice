//SCRIPTED pipeline example
//node {
//	stage('Build') {
//		echo "Build"
//	}
//	stage('Test') {
//		echo "Test"
//	}
//	stage('Integration Test') {
//		echo "Integration Test"
//	}
//}
//DECLARATIVE SYNTAX
pipeline {
//    agent any
//    agent { docker { image 'maven:3.6.3'} }
    agent { docker { image 'node:15.3'} }
    stages {
        stage("Build") {
            steps {
                sh 'node --version'
                echo "build declarative"
            }
        }
        stage("Test") {
            steps {
                echo "test declarative"
            }
        }
        stage("Integration Test") {
            steps {
                echo "integration test declarative"
            }
        }
    }
    post {
        always {
            echo "I run always"
        }
        success {
            echo "I run only for success"
        }
        failure {
            echo " I run in case of failure"
        }
    }
}