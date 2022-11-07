pipeline{
    agent any

    stages {
        
        stage('Clean') {
            steps {
                cleanWs()
            }
        }

        stage('Compile Code') {
            steps {
                sh './mvnw.cmd clean compile -e'
            }
        }

        stage('Test Code') {
            steps {
                sh './mvnw.cmd clean test -e'
            }
        }

        stage('Jar Code') {
            steps {
                sh './mvnw.cmd clean package -e'
            }
        }

        stage('Run Jar') {
            steps {
                sh './mvnw.cmd spring-boot:run'
            }
        }
    }
}