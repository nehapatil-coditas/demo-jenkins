pipeline {
    agent any

    stages {
        stage('SCM') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/nehapatil-coditas/demo-jenkins.git']])
            }
        }
        stage('Deploy to S3') {
            steps {
                script {
                    withCredentials([usernamePassword(credentialsId: 'AWS-Cred', usernameVariable: 'AWS_ACCESS_KEY_ID', passwordVariable: 'AWS_SECRET_ACCESS_KEY')]) {
                        script {
                            sh 'aws s3 sync . s3://front-end-101 --acl public-read'
                        }
                    }
                }
            }
        }
    }
}
