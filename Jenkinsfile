pipeline {
  agent any
  stages {
    stage('build') {
      agent any
       environment {
         LOG_LEVEL ='INFO'
       }
      steps {
        echo "Building Release ${RELEASE} with log level ${LOG_LEVEL} ... "
      }
    }
    stage('Test'){
      steps{
        echo "Testing Release ${RELEASE} ...."
      }
      }
    
    stage('Deploy'){
      input{
        message 'Deploy'
        ok 'do it'
        parameters{
          string(name : 'TARGET_ENVIRONMENT', defaultValue: 'PROD', description: 'Target deployment environment')
        }
      }
      steps{
        echo "Deplying  Release ${RELEASE} to environment ${TARGET_ENVIRONMENT} ...."
      }
      }
  
  
  }
post {
  always{
    echo "Prints whether deploy was success or failure"
  }
}
  environment {
    RELEASE = '20.05'
  }
}

