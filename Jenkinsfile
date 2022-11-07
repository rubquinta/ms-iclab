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
                echo 'Compiling Code'
                sh './mvnw.cmd clean compile -e'
            }
        }

        stage('Test Code') {
            steps {
                echo 'Testing Code'
                sh './mvnw.cmd clean test -e'
            }
        }

        stage('Package') {
            steps {
                sh './mvnw.cmd clean package -e'
            }
        }

        stage('Execute Jar') {
            steps {
                sh './mvnw.cmd spring-boot:run'
            }
        }
    }
}
