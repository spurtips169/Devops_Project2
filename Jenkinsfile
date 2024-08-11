pipeline {
    agent {
        node {
            label 'maven'
        }
    }

    stages {
        stage('Clone-code') {
            steps {
                git 'https://github.com/spurtips169/Devops_Project2.git'
            }
        }
    }
}