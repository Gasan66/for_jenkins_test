pipeline {
    agent {
        label 'linux'
    }
    stages {
        stage('checkout role'){
            steps{
                dir('mnt-homeworks-ansible') {
                    git credentialsId: '1a426d9e-fab0-4b28-9fd6-f20ea93a78e2', url: 'git@github.com:Gasan66/for_jenkins_test.git'
                }
            }
        }
        stage('Install molecule') {
            steps{
                dir('mnt-homeworks-ansible'){
                    sh 'pip3 install -r test-requirements.txt'
                }
                sh "echo =============="
            }
        }
        stage('Run Molecule'){
            steps{
                dir('mnt-homeworks-ansible'){
                    sh 'molecule test'
                }
            }
        }
    }
}