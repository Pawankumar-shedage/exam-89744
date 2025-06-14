pipeline {
    agent any
    
    stages {
        stage('Pull data form git') {
            steps {
                git branch: 'main', url: 'https://github.com/Pawankumar-shedage/exam-89744.git'
            }
        }
        
        stage ('Build image') {
            steps {
                sh 'docker build -t gaming7761/exam_nginx_1 .'
            }
        }
    }

 }
