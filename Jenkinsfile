pipeline {
    agent {
        docker {
            image 'node:13-alpine' 
            args '-p 3000:3000' 
        }
    }
    stages {
	stage('Snyk Scan') {
		steps {
			snykSecurity monitorProjectOnBuild: false, projectName: 'simple-node-js-react-npm-app', snykInstallation: 'snyk@latest', snykTokenId: 'Synk Token'
		}
	}
        stage('Build') { 
            steps {
		sh 'npm install' 
            }
        }
    }
}
