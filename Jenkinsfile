pipeline {
    agent any

    tools {
        gradle 'Gradle'  
        jdk 'JDK'        
    }

    stages {
        stage('Checkout') {
            steps {
               
                git branch: 'master', url: 'https://github.com/shar4440/MavenToGradle2.git'
            }
        }

        stage('Build') {
            steps {
                
                sh './gradlew clean build'
            }
        }

        stage('Run Jar') {
            steps {
               
                sh 'java -jar build/libs/MyMavenToGradle2-1.0-SNAPSHOT.jar'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully.'
        }
        failure {
            echo ' Pipeline failed.'
        }
    }
}
