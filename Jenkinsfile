pipeline{
  agent any
  parameters{
     string(name: 'BRANCH', defaultValue: 'master', description: 'Specify Branch to Build')
  }
  stages{
    stage('Checkout'){
      steps{
        git branch: "${params.BRANCH}", credentialsId: 'GITHUB_ahladh', url: 'https://github.com/ahladh/java-maven-junit-helloworld.git'      }
    }
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
