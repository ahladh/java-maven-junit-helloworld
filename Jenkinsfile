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
              junit 'target/surefire-reports/*.xml'
              junit 'target/failsafe-reports/*.xml' 
      }
    }
  
  }
}
