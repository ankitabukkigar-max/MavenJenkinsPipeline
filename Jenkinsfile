pipeline {
    agent any


    stages {

        stage('Checkout') {
            steps {
                git branch: 'master', url: 'http://github.com/ankitabukkigar-max/MavenJenkinsPipeline.git'
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

        stage('Run Application') {
            steps {
                sh 'java -jar target/MavenJenkinsPipeline-1.0-SNAPSHOT.jar'
            }
        }
    }

    post {
        success {
            echo 'Build successful!'
        }

        failure {
            echo 'Build failed!'
        }
    }
}
