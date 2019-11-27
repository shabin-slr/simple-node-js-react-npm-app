pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3000:3000' 
        }
    }
    stages {
	stage('Snyk Scan') {
		steps {
			monitorProjectOnBuild: false, snykSecurity projectName: 'simple-node-js-react-npm-app', snykInstallation: 'snyk@latest', snykTokenId: 'Synk Token'
		}
	}
        stage('Build') { 
            steps {
		sh 'npm install' 
            }
        }
    }
}
