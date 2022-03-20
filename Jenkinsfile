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
                cd $WORKSPACE/docker-development-youtube-series/python
                docker build . --network host -t teclinux/python:${BUILD_NUMBER}
                '''
            }
        }



    }
}  