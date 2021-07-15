pipeline {
    agent any
   

    stages {
        stage('Package') {
            steps {
            	sh 'mvn clean'
                sh 'mvn package' 
            }
        }
        stage('Publish') {
            steps {
                archiveArtifacts '**/target/*.jar'
            }
        }
        
    }
    
    post {
        always {
            junit '**/surefire-reports/*.xml'
                 
        }
    }
}
