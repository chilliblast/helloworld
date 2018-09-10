#!groovy 

pipeline {
    agent any

    tools {nodejs "NodeJS 4.4.5"}

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
		sh 'npm config set registry http://registry.npmjs.org/'
		sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Mocha Testing..'
		sh './node_modules/mocha/bin/mocha'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
	stage('Cleanup') {
	    steps {
                echo 'Cleaning up....'
		sh 'npm prune'
		sh 'rm node_modules -rf'
            }   
        }
    }
}
