pipeline {

    agent any

    tools {nodejs "nodejs_jenkins"} 
    
    stages {
        
        stage('Checkout') {
            steps {
                git 'https://github.com/huzi0906/Jenkins_Practice_Node_App.git'
            }
        }

        stage('Dependency Installation') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                echo 'npm build'
            }
        }

        stage('Test') {
            steps {
                echo 'npm run test'
            }
        }

         stage('Initialize_Docker'){
            steps{
                script{
                    env.PATH = "/usr/bin/docker"
                }
            }
        }

        stage('Containerize') {
            steps {
                sh "docker compose up"        
            }
        }

        stage('kill') {
            steps {       
                sh "docker compose down"
            }
        }

    }
}
