pipeline {
    agent {label "jenkins-agent-00001pvz9n2ko"} 
    stages {
        stage('Build') { 
            agent {
                docker {
                    image 'python:2.7.18-buster' 
                }
            }
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py' 
                stash(name: 'compiled-results', includes: 'sources/*.py*') 
            }
        }
    }
}