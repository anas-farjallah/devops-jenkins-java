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

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh '''
                        mvn sonar:sonar \
                        -Dsonar.projectKey=devops_project \
                        -Dsonar.host.url=http://192.168.56.10:9000
                    '''
                }
            }
        }
    }
}
