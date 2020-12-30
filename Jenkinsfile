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
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'ng test --watch=false --browsers=ChromeHeadless'
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'ng build --prod'
            }
        }
        stage('Deploy') {
            steps {
                ansiblePlaybook installation: 'ansible2', inventory: 'dev.inv', playbook: 'ansible_config_p4.yml'
            }
        }
    }
}
