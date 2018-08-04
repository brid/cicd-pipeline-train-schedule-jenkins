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
        stage('Jenkins Scripts') {
            steps {
                echo 'Call some Jenkins scripts here'
            }
        }
    }
}
