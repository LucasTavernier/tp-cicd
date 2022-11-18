pipeline{
    agent any
    stages{
        stage('Clean and Build'){
            steps{
                bat 'mvn --version'
                bat 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') { 
            steps {
                bat 'mvn package' 
            }
        }
    }
}
