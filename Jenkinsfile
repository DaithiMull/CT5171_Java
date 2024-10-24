pipeline {
    agent any

    stages {
        stage('GetProject') {
            steps {
                git 'https://github.com/DaithiMull/CT5171_Java.git'
            }
        }

        stage('Build') {
            steps {
                // Run Maven on an agent on Linux Machine with Maven installed.
                sh 'mvn clean:clean'
                sh 'mvn dependency:copy-dependencies'
                sh 'mvn compiler:compile'

                // To run Maven on a Windows agent, use bat instead of sh
                // bat 'mvn clean'
            }
        }

        stage('Exec') {
            steps {
                sh 'mvn exec:java'
            }
        }
    }
}
