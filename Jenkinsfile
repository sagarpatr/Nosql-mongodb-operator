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
}