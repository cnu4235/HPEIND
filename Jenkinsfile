pipeline {
    agent any
    tools { 
        maven 'Maven 3.9.6' 
        // jdk '9.0.4'
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
			echo "Maven is clening and gnerating artifactory"
			sh 'mvn clean package'
			}
		}
	stage ('Build docker Image') {
		steps {
			
			echo "building docker image"
			sh 'docker build -it --name test/tomcat'

			}
		}

	
    }
}
