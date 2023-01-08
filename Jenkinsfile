pipeline {
    agent any 

    stages{
        stage("one"){
            steps{
                echo 'step 01'
                sleep 3
            }
        }
        stage("two"){
            steps{
                echo 'step 02'
                sleep 9
            }
        }
        stage("three"){
            when{
                branch 'master'
                changeset "**/worker/**"
                }
                    steps{
                        echo 'step 3'
                        sleep 5
                    }
        }
    } 

    post{
      always{
          echo 'Pipeline completed successfully'
      }
      failure{
          slackSend (channel: "#ci-cd", message: "Build Failed: ${env.JOB_NAME} ${env.BUILD_NUMBER}")
      }
      success{
          slackSend (channel: "#ci-cd", message: "Build Success: ${env.JOB_NAME} ${env.BUILD_NUMBER}")
      }
    }
}