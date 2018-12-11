pipeline {
    agent {label 'new-jen-dine'}
   stages {
	 stage('checkout remoterepo') {
	   steps {
	        dir('./remoterepo'){
			    checkout([$class: 'GitSCM', branches: [[name: '*/master']], 
				doGenerateSubmoduleConfigurations: false, extensions: [], 
				submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/sanganateja/remoterepo']]])
				}
			}
        }
        stage('checkout devtraining') {
         	steps {
			dir('./devtraining'){
			  checkout([$class: 'GitSCM', branches: [[name: 'devlopbranch']], 
			  doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], 
			  userRemoteConfigs: [[url: 'https://github.com/sanganateja/devtraining']]])
			  }
			}  
		}
        stage('build') {
          steps {
            echo 'building'
             }
        
         }
     }
}	 

