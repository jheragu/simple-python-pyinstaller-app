pipeline {
    //agent {label "jenkins-agent"}
    agent none

    //environment {
        //DOCKERHUB_CREDENTIALS=credentials('docker_hub')
    //}
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