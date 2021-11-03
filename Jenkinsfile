import jenkins.*
import jenkins.model.*


def jobPattern = "*.*"

def matchedJobs = Jenkins.instance.items.findAll {
    job ->
    job.name =~ /$jobPattern/
}

pipeline {
    agent any
    stages {
        stage('List all jobs') {
            steps {
                echo "${matchedJobs}"
                sh 'exit 0'
            }
        }
        stage('Disable all jobs') {
            steps {
                sh 'exit 0'
            }
        }
        stage('Enable all jobs') {
            steps {
                sh 'exit 0'
            }
        }
    }
}
