import jenkins.*
import jenkins.model.*

  pipeline {
    agent any
    parameters { choice(name: 'action', choices: ['--select--', 'disable', 'enable'], description: 'Select an action to enable/disable all jobs in this jenkins instance') }
    stages {
    stage('Enable/Disable all jobs') {
      steps {
        script {
          Jenkins.instance.getAllItems(AbstractItem.class).each {
            job ->
            if (job.fullName ==~ "/disable-jobs\/?(.*)/gm"){
              println("Skipping: ${job.fullName}")
            } else {
              if (action == "disable") {
                println("Disabling: ${job.fullName}")
                job.doDisable()
              } else if (action == "enable") {
                println("Enabling: ${job.fullName}")
                job.doEnable()
              } else {
                println ("Do not perform any operation without an action selected: ${job.fullName}")
              }
            }
          }
        }
      }
    }
  }
}
