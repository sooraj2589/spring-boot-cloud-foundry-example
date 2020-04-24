
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
                pushToCloudFoundry(
                    target: 'api.local.pcfdev.io',
                    organization: 'Apple_Inc._devops-explore',
                    cloudSpace: 'Devops_Sandbox',
                    credentialsId: '02a189f3-e669-4579-858f-2f15adccbf72',
                //    selfSigned: true, // default value is false
                    pluginTimeout: 240, // default value is 120
                //    servicesToCreate: [
                //      [name: 'mysql-spring', type: 'p-mysql', plan: '512', resetService: true]
                //    ],
                //    envVars: [
                //      [SPRING_PROFILES_ACTIVE: 'cloud']
                //   ],
                    manifestChoice: [ // optional... defaults to manifestFile: manifest.yml
                        manifestFile: 'manifest.yml'
                    ]
            )
                }
        }
    }
}
