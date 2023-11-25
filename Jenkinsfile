pipeline {
    agent any
    stages {
        stage ('build docker image') {
            steps {
                sh '/usr/bin/docker image build -t mohan16032001/jenkinsdemo .'
            }
        }
        stage ('docker login') {
            steps {
                sh 'echo dckr_pat_r2ytb4za-q_TLXBdsemOP_LDdKY | /usr/bin/docker login -u mohan16032001 --password-stdin'
            }
        }
        stage ('push docker image') {
            steps {
                sh '/usr/bin/docker image push mohan16032001/jenkinsdemo'
            }
        }
        stage ('reload docker service') {
            steps {
                sh '/usr/bin/docker service update --image mohan16032001/jenkinsdemo --force myservice'
            }
        }

    }
}
