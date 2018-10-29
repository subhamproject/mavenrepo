pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /root/.m2:/root/.m2 -v /root/.m2/settings.xml:/root/.m2/settings.xml'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -s ./root/.m2/settings.xml clean compile package deploy'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
