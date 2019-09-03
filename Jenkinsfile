pipeline { 
    agent any 
    stages {
        stage('Build') { 
            steps {
                withMaven(maven : 'mvn'){
                        bat "mvn clean compile"
                }
            }
        }
        stage('Test'){
            steps {
                withMaven(maven : 'mvn'){
                        bat "mvn test"
                }

            }
        }
        stage('Deploy') {
            steps {
               withMaven(maven : 'mvn'){
                        bat "mvn deploy"
                }

            }
        }
    }
}
