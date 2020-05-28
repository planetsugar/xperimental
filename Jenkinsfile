class ReleaseFileInformation {
    String version
    String build_date 
    String git_url;
}

RELEASE_INFORMATION_FILE = 'releaseInfo.txt'
BRANCH_TO_BUILD = '*/jenkins-sample'
CREDENTIALS_TO_USE = '3f2b2440-f394-42a8-ab89-5f6fa02e086a'
GIT_URL = 'git@github.com:planetsugar/xperimental.git'

node {
     withEnv(["PATH+NODE=${tool name: 'nodejs', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'}/bin"]) {
        stage('Clean Workspace') {
            cleanWs()
        }
        stage('Checkout source') {
            checkout([$class: 'GitSCM', branches: [[name: BRANCH_TO_BUILD]], 
                doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], 
                userRemoteConfigs: [[credentialsId: CREDENTIALS_TO_USE, url: GIT_URL]]])
        }
        stage('Create/Read Release Info') {
            if (fileExists(RELEASE_INFORMATION_FILE)) {
                echo 'file exists'
            } else {
                echo 'file needs created'
            }
        }
        stage('Install') {                            
                sh 'npm install'             
        }
        stage('Build') {
            sh 'npm run-script build'
        }
        stage('Test') {
            sh 'npm run-script test'
        }
    }
}