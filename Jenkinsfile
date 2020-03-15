@Library('jenkins-shared-libraries@master') _
pipeline {
  agent any

    stages {
      stage('Initialization') {
          steps {
            deleteDir()
            checkout scm
            script{
            //  echo "[INFO] Loading JSON configuration from : ${env.WORKSPACE}/pipeline.json"
            //  inputFile = readFile("${env.WORKSPACE}/pipeline.json")
             parsedJson =  readJSON text: inputFile
             echo "[INFO] Done Loading JSON configuration"
             timer = BuildCause()
           }
              Init()

          }
      }

    stage('Build'){
        steps{
            build()
        }
      }
    stage('UnitTest'){
        steps{
            unitTest()
        }
      }
    stage('Deploy'){
        steps{
            deploy()
        }
      }





    }
  }