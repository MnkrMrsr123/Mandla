pipeline {
     agent any

     stages {
         stage('Clone SCM from Github') {
           steps {
                 echo 'Cloning code from GitHub'
                 git branch: 'main', url: 'https://github.com/Azure-Samples/tomcat10-jakartaee9.git'

             }
      }
        
         stage('Build artifact') {
              steps {
                   echo 'Building code using maven'
                   sh 'mvn clean install'

             }
       }

          stage('Deply to tomcat') {
                steps {
                     echo 'Deploying to tomcat'
                     deploy adapters: [tomcat7(credentialsId: 'Deployment', path: '', url: 'http://3.95.158.23:8080/')], contextPath: 'Tomcat', war: '**/*'

             }
   
       }

             }
          
        }
