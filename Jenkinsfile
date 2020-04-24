pipeline {
    agent none 
    stages {
        stage('Git Checkout') {
            steps {
                git credentialsId: 'github', url: 'https://github.com/sooraj2589/spring-boot-cloud-foundry-example.git'

            }
        }
        stage('Example Test') {
            steps {
                echo 'Hello, JDK'
                sh 'java -version'
            }
        }
    }
}
