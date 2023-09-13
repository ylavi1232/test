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
                sh 'python3 -m pytest'
            }
        }
        parallel {
            stage("hello world"){
                steps{
                    echo "hello world"
                }
            }
            stage("hello world 2"){
                steps{
                    echo "hello world 2"
                }
            }
        }
    }
}
