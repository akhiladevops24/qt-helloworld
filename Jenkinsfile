pipeline {
    agent { label '' }
    stages {
        stage('SCM') {
            steps {
                git 'https://github.com/akhiladevops24/hello-world-war.git'
            }
        }
        stage('Build') {
            steps {
                sh script: "mvn clean package"
            }
        }
        stage('postbuild') {
            steps {
                archiveArtifacts 'target/hello-world-war-1.0.0.war'
            }
        }

    }
}