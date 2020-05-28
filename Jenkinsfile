import java.io.File 


class ReleaseFileInformation {
    String version
    String build_date 
    String git_url;
}

RELEASE_INFORMATION_FILE = 'releaseInfo.txt';

node {
     withEnv(["PATH+NODE=${tool name: 'nodejs', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'}/bin"]) {
        stage('Checkout source') {
            checkout([$class: 'GitSCM', branches: [[name: '*/jenkins-sample']], 
                doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], 
                userRemoteConfigs: [[credentialsId: '3f2b2440-f394-42a8-ab89-5f6fa02e086a', url: 'git@github.com:planetsugar/xperimental.git']]])
        }
        stage('Create/Read Release Info') {
            if (fileExists(RELEASE_INFORMATION_FILE)) {
                echo 'file exists'
            } else {
                echo 'file needs created'
            }
            // sh 'touch releaseInfo.txt'
         }
         stage('Install') {                            
                sh 'npm install'             
        }
        stage('Build') {
            sh 'npm run-script build'
        }
        stage('Clean Workspace') {
            cleanWs()
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