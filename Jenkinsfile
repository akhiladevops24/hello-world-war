pipeline {
    agent { label '' }
    triggers {
        cron('H * * * 1-5')
    }
    stages {
        stage('SCM') {
            steps {
                git 'https://github.com/akhiladevops24/hello-world-war.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('postbuild') {
            steps {
                archiveArtifacts 'target/hello-world-war-1.0.0.war'
            }
        }

    }
}
