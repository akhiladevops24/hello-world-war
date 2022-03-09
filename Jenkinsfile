pipeline {
    agent { label '' }
    triggers {
        cron('H * * * 1-5')
    }
    parameters {
        string(name: 'MAVENGOAL', defaultValue: 'clean package', description: 'Enter your maven goal')
    }
    options {
        timeout(time: 30, unit: 'MINUTES') 
    }
    stages {
        stage('SCM') {
            steps {
                git 'https://github.com/akhiladevops24/hello-world-war.git'
            }
        }
        stage('Build') {
            steps {
                sh script: "mvn ${params.MAVENGOAL}"
            }
        }
        stage('postbuild') {
            steps {
                archiveArtifacts 'target/hello-world-war-1.0.0.war'
            }
        }

    }
}
