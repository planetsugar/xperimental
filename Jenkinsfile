node {
    stage('Install') {
        try {
            sh 'npm install'
        }
        catch (exc) {
            echo 'Something failed, I should sound the klaxons!'
            throw
        }
    }
     stage('Build') {
        try {
            sh 'npm run-script build'
        }
        catch (exc) {
            echo 'Something failed, I should sound the klaxons!'
            throw
        }
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