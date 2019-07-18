pipeline { 
    agent any 
    stages {
        stage('Clone repository') { 
            steps { 
                git url: 'git@github.com:begun74/test.git'
            }
        }
	stage('Deploy') {
		steps {
		        sh "ls -la "

			echo env.BRANCH_NAME 

			script {
		  		try {
     				  sh "git checkout -b f_01"
		  		} catch (Exception e) {
		      		  sh "git branch -D f_01"
		  		}
			}
				
        	}       
        }
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
        }
    }
    post {
            success {
                slackSend (channel: '#jenkins_news',color: '#00FF00', message: "SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")            
            }            
            failure {                
                slackSend (channel: '#jenkins_news',color: '#FF0000', message: "FAILED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")            
            }        
    }
}
