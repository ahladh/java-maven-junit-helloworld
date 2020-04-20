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
              junit '**/target/surefire-reports/*.xml'
              junit '**/target/failsafe-reports/*.xml' 
              publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'target/site/jacoco-both/', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: ''])
      }
    }
  
  }
}

      }
    }
  
  }
}
