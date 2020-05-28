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

pipeline {
    agent any
    tools {nodejs "node"}
    stages {
        stage('Initialise Release Information') {

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
}