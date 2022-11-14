pipeline
{
    	agent any
		stages {
			stage('Pull') {
				steps{
				script{
				checkout([$class: 'GitSCM', branches: [[name: '*/master*']],
				userRemoteConfigs: [[
				credentialsId: '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',
				url: 'https://github.com/mannai-dev/Myapp.git']]])


				}
			}
		}
		stage('npm-Install') {
             steps{
                script{
                    sh "sudo npm install"
                }
            }
        }
 			
			stage('build') {
				steps{

				script {sh "ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml "}
				}
				} 

      			stage('docker'){
         			steps {
                         	script{sh "ansible-playbook Ansible/docker.yml -i Ansible/inventory/host.yml "}
                        	}
  				}
  			}	
  }			
