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
               //withMaven(maven : 'mvn'){
                 //       sh "mvn deploy"
                //}
                 azureFunctionAppPublish appName: 'Azurefunction',
                             azureCredentialsId: 'c9c8631b-efcb-4367-9170-c89b3b95bc4b',
                             filePath: '**/*.json,**/*.jar,bin/*,HttpTrigger-Java/*',
                             resourceGroup: 'myResourceGroup',
                             sourceDirectory: 'target/'

            }
        }
    }
}
