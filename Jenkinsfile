pipeline { 
    agent any 
    stages {
        stage('Clone repository') { 
            steps { 
                git url: 'git@github.com:begun74/test.git'
            }
        }
        stage('Checking repository'){
            steps { 
                sh "ls -l"
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
}