pipeline {
    agent any
    tools {
        jdk 'JAVA_HOME'
        maven 'M2_HOME'
    }
    stages {
        stage('GIT') {
            steps {
                git branch: 'master',
                url: 'https://github.com/ziedtabib/atelierGit.git'
            }
        }
        stage('Compile') {
            steps {
                sh 'mvn clean compile'
            }
        }
        	/*stage('MVN SONARQUBE'){
		steps {
		                sh 'mvn sonar:sonar -Dsonar.login=squ_4d188daac67c5183c6ae96c9b184ad07799239d6 -Dmaven.test.skip=true'
	
    }
}*/
stage('MVN Nexus') {
            steps {
                sh 'mvn deploy -Dmaven.test.skip=true'
            }
        }
	
    }
}
