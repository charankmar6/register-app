pipeline {
    agent { label 'Jenkins-Agent' }
    tools {
        jdk 'Java'
        maven 'Maven'
    }
    stages{
        stage("Cleanup Workspace"){
                steps {
                cleanWs()
                }
        }

        stage("Checkout from SCM"){
                steps {
                    git branch: 'main', credentialsId: 'git-pwd', url: 'https://github.com/charankmar6/register-app'
                }
        }

        stage("Build Application"){
            steps {
                sh "mvn clean package"
            }

       }

       stage("Test Application"){
           steps {
                 sh "mvn test"
           }
       }   
   }
}
