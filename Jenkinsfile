pipeline{
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
               bat 'mvn -B test'
            }
        }
        stage('Deliver') {
            steps {        
                script{
                def output = bat (script: 'java -jar target/myapp-1.0-SNAPSHOT.jar', returnStdout: true).trim()
                echo "Message from Java application: ${message}"
                }
            }
        }
    }

}