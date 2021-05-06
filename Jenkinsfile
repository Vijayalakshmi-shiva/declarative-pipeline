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
        echo "Testing Release ${RELEASE} with log level ${LOG_LEVEL} not visible ... "
      }
      }
  }
  environment {
    RELEASE = '20.05'
  }
}
