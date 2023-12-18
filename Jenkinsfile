pipeline {
  agent any

  stages {
      stage('Build Artifact') {
            steps {
              sh "mvn clean package -DskipTests=true"
              sh "echo testing from mylab webhook"
              archive 'target/*.jar' //so that they can be downloaded later
            }
        }   
    }
}
