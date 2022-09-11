pipeline {
    agent any

    triggers {
  pollSCM '* * * * *'
}

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
          stage('devqatest1') {
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