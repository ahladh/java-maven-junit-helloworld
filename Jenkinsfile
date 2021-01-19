pipeline{
  agent {
      docker {
      image 'maven:3.6.3-openjdk-8'
      args '-u root:root'
    }
  }
  
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
              publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'target/site/jacoco-both/', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: ''])
      }
    }
  
  }
}
