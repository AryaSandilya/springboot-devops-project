pipeline {

    agent any

    stages {

        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/AryaSandilya/springboot-devops-project.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t petclinic:v1 .'
            }
        }
    }
}
