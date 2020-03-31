pipeline {
  agent {
    kubernetes {
      label 'mongodb-pod'
      containerTemplate {
        name 'mongodb-pod'
        image 'dtzar/helm-kubectl'
        ttyEnabled true
        command 'cat'
      }
    }
  }
  stages {
    stage('Run helm') {
      steps {
        container('mongodb-pod') {
                    echo "Check out mysql-operator code testing again in gke"
                    git url: 'https://github.com/sagarpatr/Nosql-mongodb-operator.git', branch: 'master', credentialsId: 'github-test'
                    sh '''
                    PACKAGE=mysql-operator
		
		    kubectl get deploy,svc tiller-deploy -n kube-system
		    echo "version helm"
		    helm version 
		    
                    # helm plugin install https://github.com/belitre/helm-push-artifactory-plugin --version v1.0.0
                    # helm repo add helm http://104.154.141.85:32445/artifactory/helm --username admin --password Welcome@123
		    # cd /home/jenkins/agent/workspace/mysql-operator
	            # cp -r operator ./chart/mysql-operator/
		    # cd ./chart/mysql-operator/
		    # cat values.yaml ./operator/backup.yaml ./operator/cr.yaml ./operator/operator.yaml ./operator/rbac.yaml  ./operator/secrets.yaml >> values-temp.yaml
		    # mv values-temp.yaml values.yaml
		    # rm -f -r operator
                    # cd /home/jenkins/agent/workspace/mysql-operator/chart/mysql-operator
		    #cd /home/jenkins/agent/workspace/mysql-operator/chart
                    # helm dependency update
                    # helm package .
                    helm list
                    # helm push-artifactory mysql-operator-1.0.0.tgz helm --skip-reindex
                    echo "pushed in atrifactory"
                    # helm repo update
                                        
                    
                    #DEPLOYED=$(helm list |grep -E "mysql-operator15" |grep DEPLOYED |wc -l)
                    #if [ $DEPLOYED == 0 ] ; then
                    #helm install mysql-operator15 mysql-operator --namespace=pxc
                    #else
                    #helm upgrade mysql-operator15 mysql-operator --namespace=pxc
                    #fi
                 
                    echo "deployed!"
                    '''
        }
      }
    }
  }
}
