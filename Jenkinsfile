pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/jahnavi1098/Jenkins.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Run Application') {
            steps {
                sh 'pkill -f simple-java-app || true'
                sh 'nohup java -jar target/simple-java-app-1.0.0.jar --server.port=8081 > app.log 2>&1 &'
            }
        }
    }
}