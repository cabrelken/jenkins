pipeline {
     agent { docker 'maven:3.9.3-eclipse-temurin-17' }
   
    stages {
        stage('Installation de maven') {
            steps {
                sh 'mvn -v'
            }
        }

        stage('clean et Installation les dependances') {
            steps {
                withMaven{
                sh 'mvn clean '
                }
            }
        }
         stage('Execution des tests') {
            steps {
                withMaven{
                sh 'mvn  test'
                }    
            }
        }
       
    }
     post{
            always{
                echo 'affichage des rapports'
            }
        }
}