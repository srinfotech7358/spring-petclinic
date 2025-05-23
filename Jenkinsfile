pipeline {
   
agent any
    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/srinfotech7358/spring-petclinic.git'
            }
        }
        
          stage('Build') {
            steps {
               bat 'mvn clean install'
            }
        }
          stage('Test') {
            steps {
               bat 'mvn test'
            }
        }
        
          stage('Generate Junit Test Results') {
            steps {
               junit 'target/surefire-reports/*.xml'

            }
        }
        
          stage('Generate Artifacts') {
            steps {
               archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
            }
        }
    }
}
