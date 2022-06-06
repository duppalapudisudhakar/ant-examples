pipeline {
    agent any
    tools { 
        ant 'ant_1.10' 
        jdk 'jdk_11' 
    }
    
    stages{
        stage('clean workspace'){
            steps{
            cleanWs()
            }
        }
        stage('checkout scm'){
            
            steps{
                git branch: 'main', credentialsId: 'github-token', url: 'https://github.com/DevOps-2022-001/ant-examples.git'
            }
        }
        stage('clean'){
            steps{
                sh 'ant clean'
            }
        }
        stage('compile'){
            steps{
                sh 'ant compile'
            }
        }
        stage('jar'){
            steps{
                sh 'ant jar'
            }
        }
        stage('run'){
            steps{
                sh 'ant run'
            }
        }
    }
    
    
}