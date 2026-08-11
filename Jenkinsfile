pipeline {
    agent any

    stages {
        stage('Instalação das dependências') {
            steps {
                echo 'Instalando dependências do projeto...'
                bat 'npm install'
            }
        }

        stage('Execução dos testes') {
            steps {
                echo 'Executando os testes...'
                bat 'npm test'
            }
        }
    }

    post {
        success {
            echo 'Build e testes concluídos com sucesso!'
        }
        failure {
            echo 'Ocorreu um erro durante a execução do pipeline.'
        }
    }
}