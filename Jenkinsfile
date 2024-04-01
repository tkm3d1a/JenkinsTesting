pipeline{
    agent any
    tools{
        maven "maven_3_9_6"
    }
    stages{
        stage("Mvn Test"){
            steps{
                bat "mvn -version"
            }
        }
    }
}