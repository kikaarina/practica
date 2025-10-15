pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Obteniendo el código fuente con credencial...'
                
                // Clona un repositorio de Git usando una credencial guardada en Jenkins.
                // DEBES REEMPLAZAR:
                // 1. La URL con la de tu repositorio.
                // 2. 'github-token-id' con el ID que le diste a tu credencial en Jenkins.
                git url: 'https://github.com/kikaarina/practica.git', 
                    branch: 'main', 
                    credentialsId: 'tokengit' 
            }
        }

        stage('Build') {
            steps {
                echo 'Iniciando la compilación...'
                sh 'echo "Compilando el proyecto..."'
            }
        }

        stage('Test') {
            steps {
                echo 'Ejecutando pruebas...'
                sh 'echo "Ejecutando pruebas unitarias..."'
            }
        }
    }
    
    post {
        always {
            echo 'El pipeline ha finalizado.'
        }
        success {
            echo 'El pipeline se completó con éxito.'
        }
        failure {
            echo 'El pipeline ha fallado.'
        }
    }
}
