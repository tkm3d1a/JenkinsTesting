pipeline{
    agent any
    tools{
        maven "maven_3_9_6"
    }
    stages{
        stage("Maven - Install"){
            steps{
                bat "mvn -version"
                bat "mvn clean install"
            }
        }

        stage("Docker - Build"){
            steps{
                bat "docker build -t tkm3d1a/jenkins-test:1.0.0 ."
            }
        }

        stage("Docker - Push"){
            steps{
                script{
                    withCredentials([usernamePassword(credentialsId: 'docker-login', passwordVariable: 'dockerPassword', usernameVariable: 'dockerUsername')]){
                        bat "docker login -u %dockerUsername% -p %dockerPassword%"
                        bat "docker push tkm3d1a/jenkins-test"
                    }
                }
            }
        }
    }
    post{
        always{
            cleanWs()
        }
    }
}