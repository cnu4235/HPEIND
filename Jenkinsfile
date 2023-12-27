pipeline {
    agent any
    tools { 
        maven 'Maven 3.9.6' 
        jdk '9.0.1'
    }

    stages {
	stage('Clean') {
		steps {
			cleanWs()
			}
		}
        stage('Checkout') {
            	steps {
		   // checkout scm
                git branch: 'main', changelog: false, credentialsId: 'a32543a6-a269-49f0-bee7-2ca724286117', url: 'https://github.com/cnu4235/HPEIND.git'
            }
        }
	stage ('Build') {
		steps {
			sh 'mvn clean'
			}
		}
    }
}
