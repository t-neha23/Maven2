pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/t-neha23/Maven2.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn package'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts 'target/*.jar'
            }
        }

        stage('Deploy') {
            steps {
                bat 'ansible-playbook -i inventory.ini deploy.yml'
            }
        }
    }
}
