pipeline {
  agent { label 'linux' }
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  
  parameters { 
    string(name: 'APP_NAME', defaultValue: '', description: 'What is the Heroku app name?') 
  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t devops/java-web-app:latest .'
      }
    }
    stage('Deploy') {
      steps {
        sh 'docker run -it -p 5000:5000 devops/java-web-app:latest'
      }
    }
    
  
  }
