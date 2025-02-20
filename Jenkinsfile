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
        	stage('MVN SONARQUBE'){
		steps {
		sh 'mvn sonar:sonar -Dsonar.login=admin -Dsonar.password=Zied@1234567 -Dmaven.test.skip=true';
	
    }
}
    }
}
