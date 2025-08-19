@Library(['sharedlibrary@main']) _ 

pipeline {
        agent any

        options {
            timeout(time: 10, unit: 'MINUTES')
        }

        stages {
            stage('Build from library') {
                steps {
                    echo '🔨 Compilando la aplicación...'
                    pipeline.call()
                    // Cambia esto por el comando real para tu app
                    // sh './gradlew build' // para Java/Gradle
                    // sh 'python setup.py build' // para Python
                }
            }

        post {
            success {
                echo '✅ Pipeline completado con éxito.'
            }
            failure {
                echo '❌ El pipeline falló.'
            }
        }
    }