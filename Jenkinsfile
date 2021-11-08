import jenkins.*
import jenkins.model.*

  pipeline {
    agent any
    stages {
    stage('List all jobs') {
      steps {
        script {
          def jobs = Jenkins.instance.getAllItems(AbstractItem.class)
          jobs.each {
            job ->
              println job.fullName
          }
        }
      }
    }
    stage('Disable all jobs') {
      steps {
        script {
          jobs.each {
            job ->
              job.doDisable()
          }
        }
      }
    }
    stage('Enable all jobs') {
      steps {
        script {
          jobs.each {
            job ->
              job.doEnable()
          }
        }
      }
    }
  }
}
