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
          echo 'This pipeline is completed.'
      }
    }
}