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
                sh 'docker version'
                sh 'docker build -t teclinux/api-produto -f src/PedeLogo.Catalogo.Api/Dockerfile .')
                }
        }
        
        stage('Push Image') {
            steps {
                script {
                        docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
                        dockerapp.push('latest')    
                        dockerapp.push("${env.BUILD_ID}")
                    }
                }
            }
        }     
    }
}  
