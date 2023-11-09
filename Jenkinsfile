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
        stage("Build Application") {
            steps {
                dir("/home/ubuntu") {
                    script {
                        sh "mvn clean package"
                    }
                }
            }
        }
        stage("Test Application") {
            steps {
                dir("/home/ubuntu/workspace/resume project") {
                    script {
                        sh "mvn test"
                    }
                }
            }
        }
    }
}
