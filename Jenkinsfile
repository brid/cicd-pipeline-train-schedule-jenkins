pipeline {
    agent any
    
    libraries {
        lib("jenkins-scripts@master")
    }
    
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh './gradlew build --no-daemon'
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        }
        stage('Tag') {
            steps {
                echo 'Tagging release'
                tagDeployment("cicd-pipeline-train-schedule-jenkins")
            }
        }
    }
}
