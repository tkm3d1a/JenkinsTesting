pipeline{
    agent any
    tools{
        maven "maven_3_9_6"
        docker "docker_latest"
    }
    stages{
        stage("Maven"){
            steps{
                bat "mvn -version"
                bat "mvn clean install"
            }
        }

        stage("Docker - Build"){
            steps{
                bat "docker version"
            }
        }
    }
}