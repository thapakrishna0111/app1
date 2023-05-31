pipeline{
  agent any
    environment {
    PATH="$PATH:/opt/maven/bin"
  }
    stages{
      stage('git checkout'){
        steps{
           git branch: 'main', url: 'https://github.com/koddas/app1.git'
        }
      }
      stage('UNIT Testing'){
        steps{
           sh 'mvn test'
        }
      }
     stage('Integration Testing'){
        steps{
           sh 'mvn verify -DskipUnitTests'
        }
      }
     stage('Maven Build'){
        steps{
           sh 'mvn clean install'
        }
      }
  }
}
