pipeline {
  agent any
  
  stages {
    stage('First') {
      steps {
        sh '''
        echo 'Step One'
        '''
        script {
          env.EXECUTE = 'True'
        }
      }
    }
    
    stage('Second') {
      when {
        //${env.EXECUTE}="True"
        //environment name: 'EXECUTE', value: 'True'
        expression { EXECUTE == 'True' }
      }
      steps {
        sh '''
        echo 'Step Two'
        echo 'Updating second stage'
        '''
        script {
          echo '${EXECUTE}'
        }
      }
    }
    
    stage('Third') {
      when {
        expression { EXECUTE == 'False' }
      }
      steps {
        sh '''
        echo "Step Three"
        '''
        }
      }
    }
}
