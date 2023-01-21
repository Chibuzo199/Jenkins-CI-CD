pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'scp target/*.war 3.83.100.92:8080@tomcat:/path/to/webapps'
                sh 'ssh 3.83.100.92:8080@tomcat "./bin/shutdown.sh && ./bin/startup.sh"'
            }
        }
    }
}

