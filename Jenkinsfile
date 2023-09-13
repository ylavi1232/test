#!/usr/bin/env groovy
pipeline {
    agent any
    stages {
        stage("checkout scm") {
            steps {
                echo "checkout scm"
                checkout([$class: 'GitSCM', branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/ylavi1232/test.git']]])
            }
        }
        stage("Run tests") {
            steps {
                echo "testing app"
                sh 'python3 tests/test_app.py'
            }
        }
    }
}
