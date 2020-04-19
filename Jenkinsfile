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
              junit 'src/test/java/*Test.java' 
              junit 'src/test/java/*IT.java' 
      }
    }
  
  }
}
