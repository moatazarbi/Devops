pipeline {
    agent any
    tools {
        maven 'M2_HOME'
        jdk 'JAVA_HOME'
    }
    stages {
        stage('Récupération du code') {
            steps {
                git branch: 'back',
                    credentialsId: 'github-credentials',
                    url: 'https://github.com/moatazarbi/Devops.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package -DskipTests'
            }
        }
    }
}