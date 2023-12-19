pipeline {
    agent any

    stages {
        stage('Build Artifact - Maven') {
            steps {
                sh "mvn clean package -DskipTests=true"
                sh "echo testing from mylab webhook"
                archive 'target/*.jar' 
            }
        }


        stage('Docker Build and Push') {
        steps {
          withDockerRegistry([credentialsId: docker-hub, url: ""]) {
          sh 'printenv'
           sh 'sudo docker build -t haytham1992/java-maven:""$GIT_COMMIT"" .'
           sh 'docker push haytham1992/java-maven:""$GIT_COMMIT""'
         }
        }
       }
 

    }
}



