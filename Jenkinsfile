pipeline {
    agent any
    tools {
        maven "maven"
        jdk "Javaa"
    }

    
    stages {
    stage('Fetch code'){
      steps {
        git branch: 'main', url: 'https://github.com/chiku1234560/tomcat-project..git'
      }
    }


    stage('Test'){
      steps {
        sh 'mvn package'
      }
    }
	
	stage('Deploy') {
      steps {
        //deploy war on tomcat server
        deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://51.20.116.192:8080/')], contextPath: 'tomcat-project', war: '**/*.war'
	
	
	
          }
      }

   }
}
