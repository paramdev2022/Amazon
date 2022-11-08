pipeline {
    agent any

    stages {
            stage('Build'){
            steps{
                echo 'Building........................Amazon-Project'
                dir("Amazon") {
                        sh "pwd"
                        sh 'mvn clean install -DskipTests'
                    }
                
            }
        }
        stage('test'){
            steps{
                echo 'Testing........................Amazon-Project'
                dir("Amazon") {
                        sh "pwd"
                        sh 'mvn test'
                    }
                 
            }
           post{
                always{
                    junit 'Amazon/Amazon-Core/target/surefire-reports/*.xml'
                    archiveArtifacts 'Amazon/Amazon-Web/target/*.war'
                }
            }
        }
        
    }
}
