pipeline {
    agent any

    stages {
        stage('SCM') {
            steps {
                echo 'Hello World'
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/nehapatil-coditas/demo-jenkins.git']])
             }
        }
        stage('S3 Upload') {
              steps {
                  s3Upload acl: 'PublicRead', bucket: 'front-end-101 ', cacheControl: '', excludePathPattern: '', file: 'index.html', includePathPattern: '', metadatas: [''], redirectLocation: '', sseAlgorithm: '', tags: '', text: '', workingDir: ''    
              }
        }
    }
}
