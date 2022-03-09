pipeline {
    agent { label '' }
    triggers{
        cron('59 23 * * *')
    }
    stages {
        stage('SCM') {
            steps {
                git 'https://github.com/akhiladevops24/qt-helloworld.git'
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