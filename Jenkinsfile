pipeline {
    triggers {
  pollSCM('* * * * *')
    }
   agent any
    tools {
  maven 'M2_HOME'
}

    stages {

        stage("build & SonarQube analysis") {
            agent any
            steps {
              withSonarQubeEnv('SonarServer') {
                  sh 'mvn sonar:sonar'
              }
            }
          }
        
        stage('maven package') {
            steps {
                sh 'mvn clean'
                sh 'mvn install -DskipTests'
                sh 'mvn package -DskipTests'
            }
        }
        stage('test') {
            
            steps {
                sh 'mvn test'
            }
        }
        stage('deploy') {
           
            
            steps{
                script{ 
                   echo 'deployement'
                }
            }
        }    
         
         
    }
}