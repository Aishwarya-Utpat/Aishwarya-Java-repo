pipeline {
    agent any

    stages {

        stage('Build app') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Aishwarya-Utpat/Aishwarya-Java-repo.git']])
            }
        }
        
        stage('Build docker image'){
            steps{
                script{
                    bat 'docker build -t JavaAppImage .'
                }
            }
        }
        stage('Change image tag'){
            steps{
                script{
                    bat 'docker tag JavaAppImage aishwaryautpat27/imagename:tagname'
                }
            }
        }
        stage('Push image to docker hub'){
            steps{
                script{
                   
                    bat 'docker login -u aishwaryautpat27 -p Aishwarya@27!'
                    
                    bat 'docker push aishwaryautpat27/imagename:tagname'
                }
            }
        }
    }
}
