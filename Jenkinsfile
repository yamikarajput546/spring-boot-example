
  
pipeline{
    triggers{
        pollSCM('H 0 * * 2')
     }
  agent {
    label "slave02"
  }
  
    tools { 
        maven 'apache-maven-3.6.0'
        jdk 'jdk11'
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
