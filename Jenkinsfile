pipeline{
	//triggers{
        //pollSCM('30 0 1 8 *')
     //}
    agent any
    tools { 
        maven 'maven' 
        jdk 'jdk 11'
    }
    stages{
        stage("Cleanup")
        {
            steps
            {
                sh 'mvn clean'
            }
        }
        stage("Compile")
        {
            steps{
                sh 'mvn compile'
            }
        }
        
        stage("Test")
        {
        
            steps
            {
                sh 'mvn test'
            }
        }
        stage("Package")
        {
            steps{
                sh 'mvn package'
            }
        }

    }
    post{
         always{
            mail to: 'yamikarajput.233@gmail.com',
			subject: "Pipeline: ${currentBuild.fullDisplayName} is ${currentBuild.currentResult}",
			body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}\n More info at: ${env.BUILD_URL}"
	}
       
           
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
