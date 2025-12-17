# Paralle-pipeline
pipeline {
    agent any
    stages {
        stage('Parallel Tests') {
            parallel {
                stage('Chrome Tests') {
                    steps {
                        sh 'mvn test -Dbrowser=chrome'
                    }
                }
                stage('Firefox Tests') {
                    steps {
                        sh 'mvn test -Dbrowser=firefox'
                    }
                }
            }
        }
    }
}
