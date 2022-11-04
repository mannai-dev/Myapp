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
		                sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml "
			                  }
		                   }
	                    }
	}
}

