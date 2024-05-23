pipeline {
    agent any
    stages {
        stage('git clone') {
            steps {
                git 'https://github.com/YeshwanthRamesh/Amazon'
            }
        }
        stage('build') {
            steps {
                dir('Amazon') {
                    sh 'mvn clean install'
                }
            }
        }
        stage('docker build and run') {
            steps {
                dir('Amazon') {
                    sh 'cp -r Amazon-Web/target/Amazon.war .'
                    sh 'docker build -t agni:latest .'
                    sh 'docker run -it -d -p 8088:8080 agni:latest'
                }
            }
        }
    }
}
