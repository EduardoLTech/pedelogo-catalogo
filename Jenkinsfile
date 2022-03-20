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
                script {
                    dockerapp = docker.build("teclinux/api-produto:${env.BUILD_ID}")
                }
            }
        }



    }
}  