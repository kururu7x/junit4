pipeline {
    agent any

    stages {

        stage('Stage 2 - java version') {
            steps {
                sh 'java -version'
            }
        }

        stage('gitowe') {
            steps {
                git branch: 'mavenWrapper', poll: false, url: 'https://github.com/kururu7x/junit4.git'
            }
        }

        stage('maven') {
            steps {
                sh './mvnw clean verify'
            }
        }
    }


    post {
        always {
            echo "Generate raport."
            junit '**/target/surefire-reports/*.xml'
        }
    }

}