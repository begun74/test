pipeline { 
    agent any 
    stages {
<<<<<<< HEAD
        stage('Work with repo. Deploy') { 
          steps {
	        sh "ls -la "

                	//git branch: 'feature_01', url: 'git@github.com:begun74/test.git'
			git  url: 'git@github.com:begun74/test.git'

			echo env.BRANCH_NAME 

			/*script {
		  		try {
     				  sh "git checkout -b f_01"
		  		} catch (Exception e) {
		      		  sh "git branch -D f_01"
		  		}
			}
			*/
				
          }       
        }

        stage('Work with files'){
            steps { 
                sh "ls -la"

                sh '''
                tar -zcvf /tmp/test.tar.gz  ./
                '''
                deleteDir()
                sh "mv /tmp/test.tar.gz  ./"
            }
        }

        stage('Save artifact'){
            steps { 
                sh "ls -la"
		  always {
			archiveArtifacts artifacts: '**/*', onlyIfSuccessful: true
		  }
            }
        }

        stage('Packing test') {
            steps {
                sh "ls -l"
	   }
=======
       
        stage('Checking repository'){
            steps { 
                sh "ls -la"
            }
        }
        stage('Packing project') {
            steps {
                sh '''
                tar -zcvf /tmp/package.tar.gz  ./
                '''
                deleteDir()
                sh "mv /tmp/package.tar.gz  ./"
            }
        }
        stage('Packing test') {
            steps {
                sh "ls -l"
            }
>>>>>>> f_02
        }
    }
    post {
            success {
<<<<<<< HEAD
                slackSend (channel: '#jenkins_news',color: '#00FF00', message: "SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
            }
            failure {
                slackSend (channel: '#jenkins_news',color: '#FF0000', message: "FAILED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
            }
    }
}
=======
                slackSend (channel: '#jenkins_news',color: '#00FF00', message: "SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")            
            }            
            failure {                
                slackSend (channel: '#jenkins_news',color: '#FF0000', message: "FAILED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")            
            }        
    }
}
>>>>>>> f_02
