pipeline {
  agent any
  stages {
    stage('First') {
      environment {
        EXECUTE ='True'
      }
      steps {
        
      }
      }
    stage('Second') {
      when {
        //${env.EXECUTE}="True"
        environment name: 'EXECUTE', value: 'True'
        
      }
      steps {
        echo "Updating second stage"
        
        }
      }
    stage('Third') {
      steps {
        //pendiente
        sh '''
        echo "Step Three"
        '''
        }
      }
    }
}
