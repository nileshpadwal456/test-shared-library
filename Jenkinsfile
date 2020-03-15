jsl = library(
  identifier: "jenkins-shared-library@${env.BRANCH_NAME}",
  retriever: modernSCM(
    [
      $class: 'GitSCMSource',
      remote: 'https://github.com/nileshpadwal456/jenkins-shared-library.git'
    ]
  )
)

build = jsl.com.mycompany.jenkins.Build.new(this)
git = jsl.com.mycompany.jenkins.Git.new(this)

pipeline {

  agent any

  stages {

    stage('Init') {
      steps {
        script {
          COMMIT_MESSAGE = git.commitMessage()
          COMMIT_AUTHOR = git.commitAuthor()

          build.setBuildDescription(
            message: COMMIT_MESSAGE,
            description: COMMIT_AUTHOR
          )
        }
              simplePipeline()
      }
    }


  }
}
