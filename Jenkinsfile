pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh './mvnw compile' 
            }
        }
        stage('Test') {
            steps {
                sh './mvnw test' 
            }
        }
        stage('Package') {
            steps {
                sh './mvnw package' 
            }
        }
        stage('Deploy') {
            when{
                branch 'master'
            }
            steps {
                sh './mvnw deploy' 
            }
        }
    }
    post {
    	success {
    	    slackSend(color: 'good', message: "Build Passed - Question 1 - Jake Bedard")
    	}
   }

}
