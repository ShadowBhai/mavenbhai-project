pipeline {
      agent any
      stages{
            stage('Build'){
                  steps {
                        sh 'mvn clean package'
                  }
                  post {
                        success {
                              echo 'Now Archiving'
                              archiveArtifacts artifacts: '**/*.war'
                        }
                  }
             stage('Deploy to staging'){
                   steps {
                         build job: 'Deploy-To-Staging'
                   }
             }
                        
            }
      }
}
