pipeline {
   agent any

   stages {
      stage('clean') {
         steps {
            bat 'mvn clean'
         }
      }
      stage('package') {
         steps {
            bat 'mvn install'
         }
      }
      stage('deploy') {
         steps {
            deploy adapters: [tomcat8(credentialsId: '7c7f0fc4-b2df-4edc-bbee-f795416dcace', path: '', url: 'http://localhost:9999')], contextPath: 'jenkinspipeline', war: 'productweb\\target\\productweb.war'
         }
      }
   }
  
}
}