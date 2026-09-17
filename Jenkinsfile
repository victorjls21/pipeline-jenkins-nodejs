pipeline {
    agent any

    tools {
        nodejs 'NodeJS'
    }

    stages {
        stage('Instalar Dependências') {
            steps {
                echo 'Instalando dependências...'
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                echo 'Executando Build...'
                sh 'npm run build --if-present'
            }
        }
        stage('Teste') {
            steps {
                echo 'Executando Testes...'
                sh 'npm test'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executada com SUCESSO!'
        }
        failure {
            echo 'Pipeline FALHOU! Verifique os logs.'
        }
    }
}
