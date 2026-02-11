pipeline {
    agent any

    tools {
        jdk 'JDK17'
        maven 'M2_HOME'
    }

    stages {
        stage('Build') {
            steps {
                sh 'java -version'
                sh 'mvn clean package -DskipTests'
            }
        }
    }
}
