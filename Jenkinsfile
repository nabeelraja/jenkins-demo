import jenkins.*
import jenkins.model.*

  pipeline {
    agent any
    parameters { choice(name: 'action', choices: ['disable', 'enable'], description: 'Select an action to enable/disable all jobs in this jenkins instance') }
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
    stage('Enable/Disable all jobs') {
      steps {
        script {
          Jenkins.instance.getAllItems(AbstractItem.class).each {
            job ->
            if (job.name == "disable-jobs" || job.name == "mgmt-multiregion" ){
              println("Skipping: " + job.name)
              continue
            } else {
              if (action == "disable") {
                job.doDisable()
              } else if (action == "enable") {
                job.doEnable()
              } else {
                println "Do not perform any operation without an action selected"
              }
            }
          }
        }
      }
    }
  }
}
