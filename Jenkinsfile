//SCRIPTED pipeline
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
    agent any
    stages {
        stage("Build") {
            steps {
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
}