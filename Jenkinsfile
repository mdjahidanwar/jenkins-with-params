//parameter for use external configuration 
//example - you have to build your application but you want to select the version you want to deploy
//types - string, choice, booleanparam
pipeline {
    agent any
    parameters {
//        string(name: 'VERSION', defaultValue: '', description: 'version to deploy on the production')
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: 'your message/notes')
        booleanParam(name: 'executeTests', defaultValue: 'true', description: 'your msg/notes')

    }
    stages {
        stage('build') {

            steps {
                echo 'building the application'
                

            }
        }
        stage('test') {
            when {
                expression {
                    params.executeTests == true
                }
            }
            
            steps {
                echo 'testing the application'
            }
        }
        stage('deploy') {
            steps {
                echo 'releasing the application'
                echo "depolying version ${VERSION}"
                
            }
        }


    }

    
}
