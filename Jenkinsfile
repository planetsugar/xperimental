import java.io.File 

class ReleaseFileInformation {
    String version
    String build_date 
    String git_url;
}


node {
     withEnv(["PATH+NODE=${tool name: 'nodejs', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'}/bin"]) {
         stage('Create/Read Release Info') {
            def file = new File('releaseInfo.txt') 
            // sh 'touch releaseInfo.txt'
         }
         stage('Install') {                            
                sh 'npm install'             
        }
        stage('Build') {
            sh 'npm run-script build'
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