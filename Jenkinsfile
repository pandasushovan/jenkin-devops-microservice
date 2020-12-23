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
    agent any
    //agent { docker { image 'maven:3.6.3'} }
    //agent { docker { image 'node:15.3'} }
//    environment {
//        mavenHome = tool 'myMaven'
//        dockerHome = tool 'myDocker'
//        PATH = "$mavenHome/bin:$dockerHome/bin:$PATH"
//    }
    stages {
        stage("Checkout") {
            steps {
                echo "build declarative"
                echo "BUILD ID - $env.BUILD_ID"
                echo "BUILD Name - $env.BUILD_NAME"
                echo "BUILD Tag - $env.BUILD_TAG"
                echo "PATH - $PATH"
                echo "Job Name - $env.JOB_NAME"
//                sh 'docker version'
//                sh 'mvn --version'
                bat 'docker version'
                bat 'mvn --version'
            }
        }
        stage("Compile") {
            steps {
                bat "mvn clean Compile"
            }
        }
        stage("Test") {
            steps {
                bat "mvn test"
            }
        }
        stage("Integration Test") {
            steps {
                bat "mvn failsafe:integration-test failsafe:verify"
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