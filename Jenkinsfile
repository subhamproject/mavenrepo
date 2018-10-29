pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /root/.m2:/root/.m2 -v /usr/share/maven/ref/settings.xml:/usr/share/maven/ref/settings.xml'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -s settings.xml clean compile package deploy'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
