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
                sh 'docker build -t gaming7761/exam_nginx_2 .'
            }
        }

        stage ('docker login'){
            steps {
                sh 'echo dckr_pat_kF7Lo8M9JBru8jqM01UTWVbE8os | docker login -u gaming7761 --password-stdin'
            }
        }
 
        stage('push image') {
            steps {
                sh 'docker push gaming7761/exam_nginx_2'
            }
        }
        
        //remove and start service

        stage('remove existing service') {
            steps {
                sh 'docker service rm examservice'
            }
        }

	      stage('create service') {
            steps {
                sh 'docker service create --name examservice -p 4000:4000 --replicas 2 gaming7761/exam_nginx_2'
            }
        }

    }

 }
