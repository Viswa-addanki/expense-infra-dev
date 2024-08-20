pipeline {
    agent {
        label 'AGENT-1'
    }
      options {
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
    }
    stages {
        stage('Init') {
              steps {
               sh """
                
               """
            }
        }
        stage('Plan') {
            steps {
                sh 'echo This is test'
            }
        }
        stage('Deploy') {
            steps {
               sh 'echo this is deployed'
            }
        }
      
}

 post { 
        always { 
            echo 'I will always say Hello again!'
        }
        success { 
            echo 'I will run when pipeline is success'
        }
        failure { 
            echo 'I will run when pipeline is failure'
        }
    }

}