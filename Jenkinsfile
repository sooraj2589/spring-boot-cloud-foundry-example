pipeline {
    
    agent any

    stages {

        stage("Git Checkout") {

            steps {
                git url: 'https://github.com/sooraj2589/spring-boot-cloud-foundry-example.git'

            }
        }
        
        stage("Maven Build") {
            steps {
                sh "mvn clean install"
        
            }
        }
    }
}
