pipeline {
    agent any

    tools {
        maven 'Maven'   
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/PrathwishShetty03/MymavenWebApp_test1.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Deploy WAR to Tomcat') {
            steps {
                sh 'cp target/MymavenWebApp_test1.war /opt/tomcat/webapps/'
            }
        }
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
