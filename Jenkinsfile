properties([
   pipelineTriggers([pollSCM('* * * * *')])
])

pipeline {
    agent any


    tools {
  maven 'M2_HOME'
}

    stages {
        stage('maven package') {
            steps {
                sh 'mvn clean'
                sh 'mvn install'
                sh 'mvn package'
            }
        }
          stage('devqatest') {
            steps {
                sh 'mvn test'
              
            }
        }
          stage('uattest') {
            steps {
                echo 'test'
               
            }
        }
          stage('deploy') {
            steps {
                echo 'deploy'
                
            }
        }
    }
}