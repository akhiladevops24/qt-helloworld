pipeline {
    agent { label '' }
    triggers{
        cron('H * * * 1-5')
    }
    stages {
        stage('SCM') {
            steps {
                git  branch: 'developer', url:'https://github.com/akhiladevops24/qt-helloworld.git'
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
    post {
        always {
            mail to: 'akhilakamatam.2426@gmail.com', 
                subject: "Status of pipeline ${currentBuild.fullDisplayName}",
                body: "${env.BUILD_URL} has result ${currentBuild.result}"
        }
    }
}