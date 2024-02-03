                        echo "Maven is clening and gnerating artifactory"
                        sh 'mvn clean package'
                        }
                }
        stage ('Build docker Image') {
                steps {

                        echo "building docker image"
                        sh 'docker build -t test/nginx .'
                        sh 'docker tag test/nginx cnu4235/myowncnu:nginx'
                        }
                }

          stage ('Push docker image innto dDockerhub') {
                steps {
                withCredentials([string(credentialsId: 'dockerhub_PWD', variable: 'dockerhubcreds')]) {
                        sh 'docker login -u cnu4235 -p ${dockerhubcreds}'
                    }
                        sh 'docker push cnu4235/myowncnu:nginx'
                }
        }
		

