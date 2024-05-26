pipeline {
    agent any
    tools {
        maven "maven"
        jdk "java"
    }
     stages {
        stage("Check out") {
            steps {
                script {
                    git 'https://github.com/yadhu870/jenkins-test.git'
                }
            }
        }

        stage("mvn build") {
            steps {
                script {
                    sh "mvn clean package"
                }
            }
        }
        stage("deploy to tomcat server via ansible"){
          steps{
              script {
                  sh "ansible-playbook /var/lib/jenkins/jenkins-project/playbook/tomcat.yml"
              }
          }
        }
     }
}
