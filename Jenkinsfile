pipeline {
    agent any
     tools {
        maven 'maven' 
    }
options {
    buildDiscarder(logRotator(numToKeepStr: '10')) 
}
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage(‘gitclone’) {
            steps {
               checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-token', url: 'https://github.com/priyatalent/devops-us-maven.git']])
            }
        }
stage('maven') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}
