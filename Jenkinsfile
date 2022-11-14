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
