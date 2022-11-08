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
                sh './mvnw clean compile -e'
            }
        }

        stage('Test Code') {
            steps {
                echo 'Testing Code'
                sh './mvnw clean test -e'
            }
        }

        stage('Package') {
            steps {
                sh './mvnw clean package -e'
            }
        }

        stage('Execute') {
            steps {
                sh './mvnw spring-boot:run'
            }
        }
    }
}
