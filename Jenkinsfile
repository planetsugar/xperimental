class ReleaseFileInformation {
    String version
    String build_date 
    String git_url;
}

pipeline {
    agent any
    tools {nodejs "node"}
    stages {
        stage('Install') { 
            steps {
                sh 'npm install' 
            }
        }
        stage('Build') { 
            steps {
                sh 'npm run-script build' 
            }
        } 
    }
}