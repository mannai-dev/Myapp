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
				url: ‘https://github.com/mannai-dev/Myapp.git']]])


				}
			}
		}
	}
}
