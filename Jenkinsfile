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
