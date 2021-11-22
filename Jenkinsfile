pipeline {
    agent any
     environment {
        DOCKER_CREDS=credentials('docker_id')
        }
     stages {

       stage ('Build') {
         steps {
          sh 'echo building stage'
             }
          }

       stage ('Test'){
         steps {
          sh ' docker run -t anreddy/polls_sqlite python ./mysite/manage.py test run'
            }
          }

       stage('Deploy_AWS_EBS') {
         steps {

            sh 'Echo trying AWS EBS'

           }
         }
       }
        }







