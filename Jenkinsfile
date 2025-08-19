pipeline {
    agent any

    environment {
    DEPLOY_DIR = "C:\\Users\\DAY-V\\Desktop\\app\\app"
}

    options {
        timeout(time: 10, unit: 'MINUTES')
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo '🔨 Compilando la aplicación...'
                // Cambia esto por el comando real para tu app
                sh 'npm install' // para Node.js
                // sh './gradlew build' // para Java/Gradle
                // sh 'python setup.py build' // para Python
            }
        }

        stage('Unit Tests') {
            steps {
                echo '🧪 Ejecutando pruebas...'
                // Cambia esto por tu sistema de testing
                sh 'npm test'
                // sh './gradlew test'
                // sh 'pytest'
            }
        }

        stage('Deploy') {
            when {
                branch 'main'  // Solo desplegar desde main
            }
            steps {
                echo '🚀 Desplegando la aplicación...'
                // Simulación de deploy
                sh '''
                echo "Copiando archivos..."
                mkdir -p $DEPLOY_DIR
                cp -r * $DEPLOY_DIR
                echo "Despliegue completado en $DEPLOY_DIR"
                '''
            }
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
