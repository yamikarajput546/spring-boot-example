
  
pipeline{
    triggers{
        pollSCM('H 0 * * 2')
     }
  agent {
    label "slave02"
  }
  
    
    stages{
        stage("Testing"){
            steps{
                sh 'mvn clean test'
            }
        }

    }
    post{
        // always{
        //     //echo "========always========"
        // }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
