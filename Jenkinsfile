pipeline {
	agent {
		kubernets{
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
		stage('Run helm')
			steps{
				container('mysql-pod'){
					echo "Check out mysql-operator code testing again"
					git url: 'https://github.com/sagarpatr/Nosql-mongodb-operator.git', branch: 'master', credentialsId: 'github'
					sh '''
					PACKAGE=Nosql-mongodb-operator
		   		    kubectl get deploy,svc tiller-deploy -n kube-system
		    		echo "version helm"
		    		helm version
					sh '''
				}	
			}
	}
}