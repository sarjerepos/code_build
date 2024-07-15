pipeline {
    agent any

    stages {
        stage('Git Checkout ') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/sarjerepos/kubernetes_java_deployment.git']])
            }
        }
        stage('Build productcatalogue ') {
            steps {
                dir('productcatalogue') {
                    sh 'mvn clean install -DskipTests'
            }
            }
        }
        stage('Build shopfront') {
            steps {
                dir('shopfront') {
                    sh 'mvn clean install -DskipTests'
            }
            }
        }
        stage('build stockmanager')  {
            steps {
                dir('stockmanager') {
                    sh 'mvn clean install -DskipTests'
            }
            }
        }
    }
}
