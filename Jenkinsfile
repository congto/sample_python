#!/usr/bin/env groovy

pipeline {

    agent {
        docker {
            image 'python:3.6'
            args '-u root'
        }
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'pip install -r dev-requirements.txt'
                sh 'pytest -s -r xX'
                sh 'flake8 --version' 
                sh 'flake8 --ignore E501 setup.py sample tests'
            }                    
        }
    }
}
