pipeline {
    agent {label "jenkins-agent"}
    //agent any
    stages {
        stage('Build') { 
            agent {
                docker {
                    image 'python:3.9.12-bullseye' 
                }
            }
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py' 
                stash(name: 'compiled-results', includes: 'sources/*.py*') 
            }
        }
    }
}