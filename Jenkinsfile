pipeline{
 agent any

 stages {
   
 	stage ('Build'){
 		steps {
 			withMaven(maven: 'apache-maven-3.3.9'){
 				sh 'mvn -f pom.xml clean test'
 			}
 		}
 	}
 	stage ('Deploy'){
 		steps {
 			withMaven(maven: 'apache-maven-3.3.9'){
 				sh 'mvn -f pom.xml package deploy  -Dusername=mule-training-sid -Dpassword=Qwerty67 -DskipTests -DmuleDeploy'
 			}
 		}
 	}
 }

}