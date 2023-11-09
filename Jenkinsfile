pipeline {
    agent { label 'jenkinsagent' }
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
    stages {
        stage("Cleanup Workspace") {
            steps {
                cleanWs()
            }
        }
        stage("Checkout from SCM") {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/ramanaambati/Resumeproject.git'
            }
        }
      
        stage("Test Application") {
            steps {
                sh "mvn test"
            }
        }
    }
}
