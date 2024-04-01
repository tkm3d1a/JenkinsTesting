pipeline{
    agent any
    tools{
        maven "maven_3_9_6"
    }
    stages{
        stage("Checkout Test"){
            steps{
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/tkm3d1a/JenkinsTesting']])

                bat "mvn -version"

            }
        }
    }
}