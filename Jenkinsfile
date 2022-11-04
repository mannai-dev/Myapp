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
      stage('Build') {
	              steps {
		              script{
		                sh "ansible-playbook Ansible/build.yml -i ansible/inventory/host.yml -k"
			                  }
		                   }
	                    }
	}
}

