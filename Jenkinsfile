pipeline {
    agent any
    tools {
            maven 'maven'
            jdk 'jdk 11'
        }
    stages {
        stage("Production") {
            steps {
                //echo "Production branch"
                sh "mvn clean package"
            }
        }
    }
    post {
       
        success {
            echo "Packaging successful"
        }
        failure {
            echo "Packaging unsuccessful"
        }
    }
}
