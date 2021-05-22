pipeline {
    agent any
    tools {
        nodejs "node16"
    }
    
    environment{
        NODE_ENV = 'Production'
        
    }

    stages {
        stage('source') {
            steps {
                git 'https://github.com/farislinux/sample-project.git'
            }
        }
        
        stage('build') {
            environment{
                NODE_ENV='Staging'
            }
            steps {
                echo NODE_ENV
                sh 'npm install'
            }
        }
        
        stage('saveArtifact') {
            steps {
                archiveArtifacts artifacts: '**', followSymlinks: false
            }
        }
    }
}

