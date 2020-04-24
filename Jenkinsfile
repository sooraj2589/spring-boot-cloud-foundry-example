pipeline {
    agent any

    stages {
        stage ('Build Maven') {

            steps {
                withMaven(maven : 'maven-3.6.3') {
                    sh 'mvn clean install'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven-3.6.3') {
                    sh 'mvn test'
                }
            }
        }
    }
}
