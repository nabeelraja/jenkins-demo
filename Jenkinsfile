import jenkins.*
import jenkins.model.*

  pipeline {
    agent any
    stages {
    stage('List all jobs') {
      steps {
        script {
          Jenkins.instance.getAllItems(AbstractItem.class).each {
            job ->
              println job.fullName
          }
        }
      }
    }
    stage('Disable all jobs') {
      steps {
        script {
          Jenkins.instance.getAllItems(AbstractItem.class).each {
            job ->
              job.doDisable()
          }
        }
      }
    }
    stage('Enable all jobs') {
      steps {
        script {
          Jenkins.instance.getAllItems(AbstractItem.class).each {
            job ->
              job.doEnable()
          }
        }
      }
    }
  }
}
