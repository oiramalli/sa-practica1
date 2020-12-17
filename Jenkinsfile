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
                echo 'Deploying...'
                sh 'scp -r ~/workspace/SA_P1/dist/sa-practica1 mario@puppet-agent.mjalvarado.com:~/'
                sh 'ssh mario@puppet-agent.mjalvarado.com "sudo cp -r ~/sa-practica1/. /var/www/html"'
            }
        }
        stage('Puppet') {
            steps {
                echo 'Puppet...'
                sh 'ssh mario@puppet-agent.mjalvarado.com "sudo runuser -l root -c 'puppet agent --test'"'
            }
        }
    }
}
