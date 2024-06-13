pipeline {
        agent any
        tools {
            maven 'maven00' 
            jdk 'jdk22'
            }
    stages {
	        stage('mvn check'){
	            steps{
	                script{     
	                    sh 'mvn --version'
	                    sh 'java --version'
	                    echo "Hello"
	                    sh 'rm -rf Liquibase_Test'
	                    sh 'git clone https://github.com/chrajeshdagur/Liquibase_Test.git'
	                }
	            }
	        }
	        stage('Change Dir') {
                steps {
                    dir('Liquibase_Test') {
                    sh'ls -la'
                    }
                }
            } 
	        
	        stage('Maven build') {
                steps {
					dir('Liquibase_Test') {
                    sh 'pwd'
	                sh 'mvn clean install'
                  }
                }
            } 
	        
        }   
}
