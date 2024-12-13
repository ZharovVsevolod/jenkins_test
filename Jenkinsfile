pipeline {
    agent {
        node {
            label "docker-agent-py"
        }
    }
    stages {
        stage("Build") {
            steps {
                echo "Building..."
                sh """
                echo "Some build steps"
                """
            }
        }
        stage("Test") {
            steps {
                echo "Testing..."
                sh """
                python3 hello.py
                """
            }
        }
        stage('SonarQube analysis') {
            steps {
                script {
                    scannerHome = tool 'sonar-scanner-tool'
                }
                withSonarQubeEnv(credentialsId: 'sonarqube-id', installationName: 'Sonar') {
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
    }
}