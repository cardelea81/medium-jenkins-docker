pipeline {
    agent {
        node {
          label 'docker'
        
      }
   }     docker { image 'maven:3.8.6-openjdk-11-slim' }
  }
    stages {
        stage('Build Application') {
            steps {
                sh 'mvn clean package'
            }
         post {
            success {
                echo "Now Archiving the Artifacts....."
                archiveArtifacts artifacts: '**/*.war'
            }
        }
    }
}
}
