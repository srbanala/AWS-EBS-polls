# AWS-EBS-polls

Step1: Create an application 
aws elasticbeanstalk create-application --application-name ebs-polls

Step2:Create an environment .
 aws elasticbeanstalk create-environment --environment-name ebs-polls-env --application-name ebs-polls  --solution-stack-name "64bit Amazon Linux 2 v3.4.13 running Docker" --option-settings file://options.json

##To delete application version
aws elasticbeanstalk delete-application-version  --application-name ebs-polls --version-label v6


## To create a configuration template



aws elasticbeanstalk create-configuration-template --application-name ebs-polls --template-name ebs-polls-v1 --environment-id e-7rpzuxxggy

# To creat application verion
copy file to s3 first
aws s3 cp Dockerrun.aws.new.json  s3://elasticbeanstalk-us-east-1-298693496319
aws elasticbeanstalk create-application-version --application-name ebs-polls  --version-label v4 --source-bundle S3Bucket="elasticbeanstalk-us-east-1-298693496319",S3Key="Dockerrun.aws.new.json" --auto-create-application


# TO update application

aws elasticbeanstalk update-application --application-name ebs-polls --description "my Elastic Beanstalk application"


#TO update environment.
aws elasticbeanstalk update-environment --environment-name ebs-polls-env --version-label v2