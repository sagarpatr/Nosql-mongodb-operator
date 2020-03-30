pipeline {
	agent {
		kubernetes{
			label mongodb-pod
			containerTemplate{
				name mongodb-pod
				image 'dtzar/helm-kubectl'
				ttyEnabled true
				command 'cat'
			}
		}
	}
	stages {
		stage('Run helm'){
			steps{
				
				git url: 'https://github.com/sagarpatr/Nosql-mongodb-operator.git', branch: 'master', credentialsId: 'nosql-repository'
					
			     }
		}	
	}
}
