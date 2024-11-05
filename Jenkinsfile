pipeline {
    agent any
    // Uncomment this line if you want to use a Docker agent
    // agent { docker { image 'maven:3.6.3' } }
    
    environment {
        dockerHome = tool 'myDocker'  // Make sure 'myDocker' is configured in Jenkins
        mavenHome = tool 'myMaven'    // Make sure 'myMaven' is configured in Jenkins
        PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
    }
    
    stages {
        stage('Build') {
            steps {
                sh 'mvn --version'              // Check Maven version
                sh 'docker --version'           // Check Docker version
                echo "Build"
                echo "PATH - $PATH"
                echo "BUILD_NUMBER - ${env.BUILD_NUMBER}"
                echo "BUILD_ID - ${env.BUILD_ID}"
                echo "JOB_NAME - ${env.JOB_NAME}"
                echo "BUILD_TAG - ${env.BUILD_TAG}"  // Corrected the typo from BUILF_TAG to BUILD_TAG
                echo "BUILD_URL - ${env.BUILD_URL}"  // Corrected usage of env variables
            }
        }
    }
}
				