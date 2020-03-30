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
				// container('mongodb-pod') {
					echo "Check out mongodb-operator code testing again"
					git url: 'https://github.com/sagarpatr/Nosql-mongodb-operator.git', branch: 'master', credentialsId: 'nosql-repository'
					/*
					sh '''
					PACKAGE=Nosql-mongodb-operator
		   		        kubectl get deploy,svc tiller-deploy -n kube-system
		    		        echo "version helm"
		    		        helm version
					sh '''
					*/
				}	
			}
		}	
	}
}
