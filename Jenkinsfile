pipeline {
    agent any

    stages {
        stage ('Compile') {

            steps {
                withMaven(maven : 'maven_3_5_2') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Test') {

            steps {
                withMaven(maven : 'maven_3_5_2') {
                    sh 'mvn test'
                }
            }
        }

        // Install build artifact in local repo
        stage ('Deploy') {
            steps {
                withMaven(maven : 'maven_3_5_2') {
                    sh 'mvn install'
                }
            }
        }
    }
}