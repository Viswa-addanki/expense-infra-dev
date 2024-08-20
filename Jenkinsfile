pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
        ansiColor('xterm')
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
            when {
                expression{
                    params.action == 'Apply'
                }
            }
            steps {
                sh """
                cd 01-vpc
                terraform plan
                """
            }
        }
        stage('Deploy') {
            when {
                expression{
                    params.action == 'Apply'
                }
            }
            input {
                message "Should we continue?"
                ok "Yes, we should."
            }
            steps {
                sh """
                cd 01-vpc
                terraform apply -auto-approve
                """
            }
        }

        
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
            deleteDir()
        }
        
    }
}