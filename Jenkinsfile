pipeline{
  agent any
  
  stages{
      stage('Build'){
        steps{
           sh 'mvn clean install'
        }
      }
    stage('Test'){
      steps{
              sh 'make check || true' 
              junit '**/target/surefire-reports/*.xml'
              junit '**/target/failsafe-reports/*.xml' 
              publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: '**/target/site/jacoco/com.example.javamavenjunithelloworld/*.html', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: ''])
      }
    }
  
  }
}
