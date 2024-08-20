pipeline {
    agent {
        label 'AGENT-1'
    }
      options {
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
    }
     parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('Init') {
              steps {
               sh """
                cd 01-vpc
                terraform init -reconfigure
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