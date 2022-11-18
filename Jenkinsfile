pipeline{
    agent any
    stages{
        stage('Clean and Build'){
            steps{
                sh 'mvn --version'
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') { 
            steps {
                sh 'mvn package' 
            }
        }
    }
}
