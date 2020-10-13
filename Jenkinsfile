pipeline {
     agent any
     stages {

         stage('Deploy Kubernetes Cluster') {
             steps {
				 sh 'echo "Deploying Kubernetes Cluster"'
                 sh '''
                 '''
             }
         }

stage('Deploying KUbernetes Cluster') {
			steps {
				withAWS(region:'us-west-2', credentials:'') {
					sh '''
						eksctl create cluster \
						--name CapstoneKubeCluster \
						--version 1.14 \
						--region us-west-2 \
						--nodegroup-name Ec2Nodes \
						--node-type t2.small \
						--nodes 2 \
						--nodes-min 1 \
						--nodes-max 3 \
						--node-ami auto \
					'''
				}
			}
		}

stage('Update teh Cluster KubeConfig file') {
			steps {
				withAWS(region:'us-west-2', credentials:'') {
					sh '''
						aws eks --region us-west-2 update-kubeconfig --name CapstoneKubeClluster
					'''
				}
			}
		}
     }
}
