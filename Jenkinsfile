pipeline {
    agent any
    tools {nodejs "node 17" }
    environment {
        NODE_ENV='production'
    }
    
  
    stages {
        stage('source') {
            steps {
                    git 'https://github.com/Yasarkhan1/aws_codebuild_codedeploy_nodeJs_demo.git' 
                    sh 'cat index.js'
            }
            
        }
        
         stage('build') {
             environment{
                 NODE_ENV='StagingGitTest'
             }
             
            
            steps {
             echo NODE_ENV
             withCredentials([string(credentialsId: 'f62a3661-1e55-4acf-9064-9ec983b6d846', variable: 'server')]) {
        // some block
           }
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
