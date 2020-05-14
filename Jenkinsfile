pipeline {
    agent { 
        node { label 'Node Builder' } 
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        } 
    }
}