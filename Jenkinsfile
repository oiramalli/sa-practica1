#!/usr/bin/env groovy
pipeline {
    agent {
        docker {
            image 'node'
            args '-u root'
        }
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // sh 'ng build --prod'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // sh 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Testing...'
                // sh 'npm test'
            }
        }
    }
}