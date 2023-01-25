pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
		sh '/usr/share/maven/bin/mvn clean package'
            }
        }
        stage('test') {
            steps {
                echo 'Building..'
		sh '/usr/share/maven/bin/mvn test'
            }
        }
        stage('delopy') {
            steps {
                echo 'Deploying....'
		sshagent(['Deploy'])  {
		sh "scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/Jenkins-CI-CD/target/webapp-0.2.war centos@18.234.61.47:/home/centos/apache-tomcat-7.0.94/webapps"
		 }
            }
        }
    }
}
