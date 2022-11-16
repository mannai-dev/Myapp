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
                script{ sh "sudo npm install /var/lib/jenkins/workspace/devops"  }
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
  				stage('docker_registry') {
steps{
script {


sh "ansible-playbook Ansible/docker-registry.yml -i Ansible/inventory/host.yml "


}
}
}
  			}	
  }			
