pipeline { 
    agent any 
    stages {
        stage('Build') { 
            steps {
                withMaven(maven : 'mvn'){
                        sh "mvn clean compile"
                }
            }
        }
        stage('Test'){
            steps {
                withMaven(maven : 'mvn'){
                        sh "mvn test"
                }

            }
        }
        stage('Deploy') {
            steps {
               withMaven(maven : 'mvn'){
                        sh "mvn deploy"
                }

            }
        }
    }
}
