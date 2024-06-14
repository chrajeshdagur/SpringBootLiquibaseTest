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
	                    sh 'rm -rf LiquibaseTest'
	                    sh 'git clone https://github.com/chrajeshdagur/LiquibaseTest.git'
	                }
	            }
	        }
	        stage('Change Dir') {
                steps {
                    dir('LiquibaseTest') {
                    sh'ls -la'
                    }
                }
            } 
	        
	        stage('Maven build') {
                steps {
					dir('LiquibaseTest') {
                    sh 'pwd'
	                sh 'mvn clean install'
                  }
                }
            } 
	        
        }   
}
