pipeline {
    agent any

    stages {
        stage('Checkout Source') {
            steps {
                git url:'https://github.com/EduardoLTech/pedelogo-catalogo.git', branch:'main'
            }
        } 
    

        stage('Build Image') {
            steps {
                sh script: '''
                #!/bin/bash
                docker build . --network host -t teclinux/api-produto:${BUILD_NUMBER}
                '''
            }
        }



    }
}  