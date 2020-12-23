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
                /* groovylint-disable-next-line LineLength */
                sh 'scp -r ~/workspace/SA_P1/dist/sa-practica1/* root@chef-ws.mjalvarado.com:~/chef-repo/cookbooks/cookbook_p3/files/default/dist'
            }
        }
        stage('Cheff') {
            steps {
                echo 'Cheff...'
                /* groovylint-disable-next-line LineLength */
                sh 'ssh root@chef-ws.mjalvarado.com "knife ssh \'name:chef-node-01\' \'sudo chef-client\' -x mario -P CheffP@ss"'
            }
        }
    }
}
