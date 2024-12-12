pipeline {
    agent {
        node {
            label "docker-agent-py"
        }
    }
    stages {
        stage("Build") {
            echo "Building..."
            sh """
            echo "Some build steps"
            """
        }
        stage("Test") {
            echo "Testing..."
            sh """
            echo "Some test steps"
            """
        }
    }
}