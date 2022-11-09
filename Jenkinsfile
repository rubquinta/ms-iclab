pipeline{
    agent { docker 'maven:3.8.1-adoptopenjdk-11' }

    stages {                
        stage("Clean") {
            steps {
                cleanWs()
            }
        }
        
        stage("Compile") {
            
            steps {
                echo "Compiling Code"
                sh "./mvnw clean compile -e"
            }
        }

        stage("Test Code") {
            steps {
                echo "Testing Code"
                sh "./mvnw clean test -e"
            }
        }

        stage("Package Build") {
            steps {
                sh "./mvnw clean package -e"
            }
        }

        stage("Execute") {
            steps {
                sh "./mvnw spring-boot:run"
            }
        }
    }
}
