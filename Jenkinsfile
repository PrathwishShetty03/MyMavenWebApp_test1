pipeline {
    agent any

    tools {
        maven 'Maven'   // Must match Jenkins tool name
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/PrathwishShetty03/MymavenWebApp01.git'
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
                sh '''

                echo "Copying new WAR..."
                cp target/MymavenWebApp01.war /opt/tomcat/webapps/

                
                '''
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
