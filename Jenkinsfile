pipeline {
  agent any

  stages {
      stage('Build Artifact - Maven') {
            steps {
              sh "mvn clean package -DskipTests=true"
              sh "echo testing from mylab webhook"
              archive 'target/*.jar' //so that they can be downloaded later
            }
        }

      stage('Unit Tests - JUnit and Jacoco') {
        steps {
          sh 'mvn test'
        }
        post {
          always {
            junit 'target/surefire-reports/*.xml'
            jacoco execPattern: 'target/jacoco.exec'
          }
        }
      } 

      }  
    }
