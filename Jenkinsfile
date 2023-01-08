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
            steps{
                echo 'step 03'
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