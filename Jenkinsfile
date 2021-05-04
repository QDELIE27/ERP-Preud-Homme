pipeline {
    agent any
    
    environment {
        JAVA_HOME='/usr/lib/jvm/java-1.11.0-openjdk-amd64'
    }

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
