pipeline {
  agent {
    node {
      label 'AGENT-1'
    }
  }
  environment {
    GREETING = "Hello Friday"
  }
  options {
    timeout(time:1, unit: 'SECONDS')
  }
  stages {
    stage('Build'){
      steps {
        echo 'Building...'
      }
    }
    stage('Test'){
      steps{
        echo 'Testing..'
      }
    }
    stage('Deploy'){
      steps{
        sh """
          echo " Here I have written shell script"
          echo "$GREETING"
        """
      }
    }
  }

  // post build
  post {
    always {
      echo ' I will always say Hello again!..'
    }
    failure {
      echo 'This block of scripts runs only when pipeline is failed, used generally to send some alerts'
    }
    success {
      echo ' I will say Hello when pipeline is executed successfully'
    }
  }
}