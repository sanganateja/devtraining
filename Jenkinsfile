pipeline {
   agen any
    stages {
        stage('frist') {
            steps {
                echo"Hello Iam going to start"
            }
        }
        stage('test') {
            steps {
                echo "Iam testing"
            }
        }
        stage('dockerbuild') {
		   steps {
		      sh 'docker build -t newimag-12 .'
			}
	    }
        stage("push to DTR") {
		  steps{
		   withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'ravidocker',
		   usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD']]) {
		  	
			sh """
		        docker login --username $USERNAME --password $PASSWORD
                docker push sangana/newimag-12
		      """		
			    }
            }				
	    }
    }
}	
