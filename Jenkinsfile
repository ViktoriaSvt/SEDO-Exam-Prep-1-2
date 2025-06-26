pipeline {
    agent any

    stages {
        stage('Restore') {
            when {
                anyOf {
                    branch 'main'
                    branch pattern: 'feature/.*', comparator: 'REGEXP'
                }
            }
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            when {
                anyOf {
                    branch 'main'
                    branch pattern: 'feature/.*', comparator: 'REGEXP'
                }
            }
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Test') {
            when {
                anyOf {
                    branch 'main'
                    branch pattern: 'feature/.*', comparator: 'REGEXP'
                }
            }
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
