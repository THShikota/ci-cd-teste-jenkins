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
                stage('Testes da suite 1') {
                    steps {
                        bat 'npm run teste-suite-1'
                    }
                }

                stage('Testes da suite 2') {
                    steps {
                        bat 'npm run teste-suite-2'
                    }
                }

                stage ('Testes da suite 3') {
                    steps {
                        bat 'npm run teste-suite-3'
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