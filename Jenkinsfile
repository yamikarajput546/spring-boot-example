pipeline {
    agent any

    stages {
        stage('Testing') {
            steps {
                echo 'Testing'
                
            }
          withMaven {
      sh "mvn clean test"
    }
        }
           
    }
}
