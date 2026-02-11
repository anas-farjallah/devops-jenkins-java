pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'JDK17'
    }

    stages {
        stage('Clone') {
            steps {
                echo 'Récupération du code...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Compilation Maven...'
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Tests Maven...'
                sh 'mvn test'
            }
        }
    }
}
