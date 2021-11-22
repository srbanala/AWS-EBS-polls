pipeline {
    agent any
     environmnet {
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
            

           }
         }


       }
        }


#deploy:
 # provider: elasticbeanstalk
  #region: "us-east-1"
  #app: "django-polls"
  #env: "djangopolls-env"
  #bucket_name: "elasticbeanstalk-us-east-1-298693496319"
  #bucket_path: "django-polls"
  #on:
   # branch: feature
  #access_key_id: $Aws_Access_key
  #secret_access_key: $Aws_Secret_Key




