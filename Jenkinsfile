node {
    stage('Install') {
        sh 'npm install'
    }
     stage('Build') {
        sh 'npm run-script build'
    }
}

/*def printOutGitBranch() {
    echo $GIT_BRANCH
}
pipeline {
    agent any
    tools {nodejs "node"}
    stages {
        stage('Prep') {
            steps {
                printOutGitBranch()
            }
        }
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
}*/