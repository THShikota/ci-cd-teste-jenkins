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
            parallel {
                stage('Testes no Chrome') {
                    steps {
                        bat 'npm run test-chrome'
                    }
                }

                stage('Testes no Electron') {
                    steps {
                        bat 'npx cypress run --browser electron'
                    }
                }
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