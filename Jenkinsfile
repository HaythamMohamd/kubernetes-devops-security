pipeline {
    agent any
    
    stages {

        stage('Docker Build and Push') {
            steps {
                withDockerRegistry([credentialsId: 'docker-hub', url: '']) {
                    sh 'printenv'
                    sh 'sudo docker build -t haytham1992/java-maven:""$GIT_COMMIT"" .'
                    sh 'docker push haytham1992/java-maven:""$GIT_COMMIT""'
                }
            }
        }
    }
}