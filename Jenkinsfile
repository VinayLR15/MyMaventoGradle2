pipeline {
    agent any

    tools {
        gradle 'Gradle'  // Name of the Gradle installation configured in Jenkins
        jdk 'JDK'        // Name of the JDK installation configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                echo '🔄 Cloning GitHub repository...'
                git branch: 'master', url: 'https://github.com/VinayLR15/MyMaventoGradle2.git'
                // Replace with your actual GitHub URL and branch name
            }
        }

        stage('Initialize') {
            steps {
                echo '📦 Initializing project with POM type...'
                sh 'gradle init --type pom'
            }
        }

        stage('Build') {
            steps {
                echo '🔨 Building the project...'
                sh 'gradle build'
            }
        }

        stage('Run Jar') {
            steps {
                echo '🚀 Running the generated JAR...'
                sh 'java -jar build/libs/MyMavenApp2-1.0-SNAPSHOT.jar'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline completed successfully.'
        }
        failure {
            echo '❌ Pipeline failed.'
        }
    }
}
