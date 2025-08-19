@Library(['sharedlibrary@main']) _ 

pipeline {
        agent any

    options {
        timeout(time: 10, unit: 'MINUTES')
    }

    stages {
        stage('Build from library') {
            steps {
                script {
                    echo '🔨 Compilando la aplicación...'
                    pipelineFlow.call() 
                }
            }
        }
    }
}