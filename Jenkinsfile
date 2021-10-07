pipeline {
    agent any
    stages {
        stage('Print Repo Name') {
            steps {
                  env.GIT_REPO_NAME = $env.GIT_URL.replaceFirst(/^.*\/([^\/]+?).git$/, '$1')
                  sh "exit 0"
                  echo $env.GIT_REPO_NAME
            }
        }
    }
}
