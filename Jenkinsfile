pipeline {
    agent any
    stages {
        stage ('Build') {
            steps {
                script{
                     def mvnHome =  tool name: 'maven3', type: 'maven'   
                    sh "${mvnHome}/bin/mvn clean package"    or we can use install package
	                sh 'mv target/myweb*.war target/newapp.war'  -->create artifacts and will store -->target/myweb*.war(in pom.xml file we are mentioning this myweb*.war name)  this path so we are telling to paste(mv--moving) this artifacts to-->target/newapp.war 
                }
            }
        }
        stage('Docker Build Images') { (once created maven package we create docker image to deploy container, if you want deploy war file means we can use tomcat)
            steps {
                script {
                    sh 'docker build -t naresh2603/multi:v1 .'
        
                }
            }
        }
    }
}
