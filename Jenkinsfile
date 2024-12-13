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
        stage("Run SonarQube") {
            enviroment {
                scannerHome = tool 'sonar-scanner-tool';
            }
            steps {
                withSonarQubeEnv(credentialsId: 'SonarQube', installationName: 'Sonar') {
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
    }
}