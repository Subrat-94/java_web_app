pipeline{
    agent any

    tools{
        maven 'maven3.9'
    }
    stages{
        stage("Checkout Code"){
            steps{
                git branch: 'master', url: 'https://github.com/Subrat-94/java_web_app.git'
            }
        }
        stage("Build Code"){
            steps{
                sh 'mvn clean package'
            }
        }
        stage("Deployment"){
            steps{
                deploy adapters: [tomcat9(url: 'http://54.226.249.178:8080/', credentialsId:'tomcat')] , war:'target/*.war'
            }
        }
    }
}