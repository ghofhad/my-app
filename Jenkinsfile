pipeline {
  agent any
    stages {
        stage('Pull') {
             steps{
                script{
                    checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                        userRemoteConfigs: [[
                            url: 'https://github.com/ghofhad/my-app.git']]])
                }
            }
        }
     
  stage('Install') {
             steps{
                script{
                    sh "sudo npm install"
                }
            }
        }

	stage ('Build') {
	
			steps {
			
			sh "ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml"
	
			}


	}




	stage('ng Build') {
             steps{
                script{
                    sh "sudo ng build"
                }
            }
        }


	
     }
      
      
    }
    
