pipeline{
 agent any
 environment {
  ANYPOINT_CRED_GLOBAL_JENKINS = credentials('anypoint-user-deploy-credentails')
 }
 stages{
  stage('Build'){
   steps{
    bat 'mvn clean install'
   }
  }
  stage('Test'){
   steps{
    bat 'mvn test'
   }
  }
  stage('Deploy'){
   steps{
    bat 'mvn clean package deploy -Danypoint.username="%ANYPOINT_CRED_GLOBAL_JENKINS_USR%" -Danypoint.password="%ANYPOINT_CRED_GLOBAL_JENKINS_PSW%" -DmuleDeploy'
   }
  }
 }
}