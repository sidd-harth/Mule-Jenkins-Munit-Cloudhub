pipeline{
 agent any
 environment {
    ANYPOINT = credentials('mulesoft-anypoint-platform')
 }
 stages {
   stage('Check Parameters') {
   steps {
    echo "Production App Name - ${username}"
    echo "Application Name - ${password}"

   }
  }
 	stage ('Build'){
 		steps {
 			withMaven(maven: 'apache-maven-3.3.9'){
 				bat 'mvn -f pom.xml clean install'
 			}
 		}
 	}
 	stage ('Deploy'){
 		steps {
 			withMaven(maven: 'apache-maven-3.3.9'){
 				bat 'mvn -f pom.xml package deploy  -Dusername=mule-training-sid -Dpassword=Qwerty67 -DskipTests -DmuleDeploy'
 			}
 		}
 	}
 }

}