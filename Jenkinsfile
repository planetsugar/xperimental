class ReleaseFileInformation {
    String version
    String build_date 
    String git_url;
}

BASE_DIR = '.'
RELEASE_INFORMATION_FILE = 'ReleaseInformation.txt'

def createReleaseInformationFile() {
    echo 'Create the release information file'
}

def readReleaseInformationFile() {
    echo 'Read the release information file'
}

node {
    tools {nodejs "node"}
    stage('Example') {
        try {
            sh 'exit 1'
        }
        catch (exc) {
            echo 'Something failed, I should sound the klaxons!'
            throw
        }
    }
}

/*pipeline {
    agent any
    tools {nodejs "node"}
    stages {
        stage('Initialize') {

            def releaseFileInfo = new File(BASE_DIR, RELEASE_INFORMATION_FILE);

            if (!releaseFileInfo.exists()) {
                createReleaseInformationFile();
                return;
            }

            readReleaseInformationFile();
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