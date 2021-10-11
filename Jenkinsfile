pipeline {
    agent any

    stages {
        stage('Testing') {
              
          
          withMaven {
      sh "mvn clean test"
    }
        }
           
    }
}
