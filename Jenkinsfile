#!/usr/bin/env groovy
pipeline {
    agent any
    stages {
        stage('Install') {
            steps {
                echo 'Installing...'
                npm i
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
                ng build --prod
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                ng test
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