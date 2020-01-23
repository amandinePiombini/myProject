pipeline {
    agent any
    tools {
        maven 'M3'
    }
    
    stages {
        stage('Checkout'){
            steps {
             sh 'echo "-----Checkout Stage--------"'
             git 'https://github.com/amandinePiombini/myProject.git'
            }
        }
        stage('Build'){
            steps {
             sh 'echo "-----Build Stage--------"'
             sh 'mvn clean compile'
            }
        }
        stage('Test'){
            steps {
             sh 'echo "-----Test Stage--------"'
              sh 'mvn test'
            
            }
            post {
                success {
                     junit '**/target/surefire-reports/TEST-*.xml'
                }
            }
        }
        stage('Package'){
            steps{
             sh 'echo "-----Package Stage--------"'
             sh 'mvn package'
            }
        }
    }
}
