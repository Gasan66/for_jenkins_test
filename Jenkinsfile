pipeline {
    agent {
        label 'docker'
    }
    stages {
        stage('dir checkout'){
            steps{
                dir('mnt-homeworks-ansible') {
                    git credentialsId: '1a426d9e-fab0-4b28-9fd6-f20ea93a78e2', url: 'git@github.com:Gasan66/for_jenkins_test.git'
                }
            }
        }
        stage('requirements') {
            steps{
                dir('mnt-homeworks-ansible'){
                    sh 'pip3 install -r test-requirements.txt'
                }
            }
        }
        stage('test'){
            steps{
                dir('mnt-homeworks-ansible'){
                    sh 'molecule test'
                }
            }
        }
    }
}