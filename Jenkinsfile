@Library('My-Jenkins-SharedLibrary') _
pipeline {
    agent any
       tools {
        maven 'Maven3'
    }
     environment {
        registry = "public.ecr.aws/c9x6d1e3/docker-image"
    }
    stages {
        stage ('Build Project') {
          steps {
              script{
                  java_build()
                }
            }
        }
        stage ("Build image") {
           steps {
              script {
                  build-image()
                }
            }
        }
        stage ("Build image") {
           steps {
              script {
                  docker-push()
                }
            }
        }
        stage ("Build image") {
           steps {
              script {
                  kube_deploy()
                }
            }
        }
    }
}
