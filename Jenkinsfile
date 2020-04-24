pipeline {

    agent any

    tools {

    //    jdk "Java-1.8"

        maven "Maven-3.6.3"

    }

    stages {

        stage("Git Checkout") {

            steps {
                git url: 'https://github.com/sooraj2589/spring-boot-cloud-foundry-example.git'

            }
        }

         //   stage("SonarQube analysis") {

         //   steps {
         //       withSonarQubeEnv('SonarQube') {
         //           bat 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.3.0.1492:sonar'
         //       }
         //   }
            
       // }

            stage("Execute Maven") {

            steps {
                script {

                    rtMaven.run pom: 'pom.xml', goals: 'clean install', buildInfo: buildInfo
                
                }
            }
        }

            stage("Publish build info") {

            steps {
                script {

                    server.publishBuildInfo buildInfo
                
                }

            }
        }
    }
}
