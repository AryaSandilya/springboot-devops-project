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

        stage('Deploy') {
            steps {
                sh '''
                docker rm -f petclinic || true
                docker run -d --name petclinic -p 8081:8080 petclinic:v1
                '''
            }
        }
    }
}
