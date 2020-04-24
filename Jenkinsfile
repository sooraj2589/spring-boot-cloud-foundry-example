pipeline {

    agent any
    tools {
        maven "maven-3.6.3"
    }
    stages {

        stage("Git Checkout") {

            steps {
                git url: 'https://github.com/sooraj2589/spring-boot-cloud-foundry-example.git'
            }
        }
            stage("Execute Maven") {

            steps {
                script {
                    rtMaven.run pom: 'pom.xml', goals: 'clean install', buildInfo: buildInfo
                }
            }
        }
    }
}
