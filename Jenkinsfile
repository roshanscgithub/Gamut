pipeline {
    agent any

//	tools {
//		jdk 'jdk8'
//	}
//	environment {
//		M2_INSTALL = "/usr/bin/mvn"
//	}

    stages {
        stage('Clone-Repo') {
	    	steps {
	        	checkout scm
	    	}
        }

        stage('Build') {
            steps {
                sh 'mvn install -Dmaven.test.skip=true'
            }
        }
		
        stage('Unit Tests') {
            steps {
                sh 'mvn compiler:testCompile'
                sh 'mvn surefire:test'
                junit 'target/**/*.xml'
            }
        }
	stage('Compile-create War file'){
	    steps {
		sh 'mvn package'  	
				
		}	
	
 	}
	stage('Deploy war'){
	   
	    steps{
		
		cp -r /target/gamutkart.war/. /root/Distros/apache-tomcat-9.0.87/webapps/
		
		}

	
	}
  	}
	
 	}
