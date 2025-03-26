pipeline {
    agent any  // Ejecuta en cualquier nodo disponible
    stages {
        // Etapa 1: Descargar el código
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/jmgjuanma/mi-web-jenkins.git'
            }
        }
        // Etapa 2: Validar HTML (ejemplo simple)
        stage('Test') {
            steps {
                sh '''  # Script en shell
                if ! grep -q "<title>" index.html; then
                    echo "❌ ERROR: No se encontró <title> en HTML"
                    exit 1
                else
                    echo "✅ HTML válido"
                fi
                '''
            }
        }
        // Etapa 3: Simular despliegue
            stage('Deploy') {
                steps {
                sh 'echo "🎉 Se desplegaría en un servidor real (ej: Nginx)"'
                }
            }
        }
    }
