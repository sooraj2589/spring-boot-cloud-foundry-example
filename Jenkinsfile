pipeline {

    agent any
    tools {
        maven "maven-3.6.3"
    }
    stages {

//        stage("Clone Git repo") {

//            steps {
//                git url: 'https://github.com/sooraj2589/spring-boot-cloud-foundry-example.git'
//            }
//        }
        stage("Build Stage") {

            steps {
                sh 'mvn clean install'
                }
        }

        stage("Testing Stage") {

            steps {
                sh 'mvn test'
                }
        }
        stage("Deployment Stage") {

            steps {
                sh 'mvn deploy'
                }
        }
    }
}
