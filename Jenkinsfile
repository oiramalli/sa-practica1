#!/usr/bin/env groovy
pipeline {
    agent any
    stages {
        stage('Install') {
            steps {
                echo 'Installing...'
                sh 'npm i'
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'ng build --prod'
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