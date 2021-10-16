pipeline {
    agent { docker { image 'php' } }
    stages {
        stage('build') {
            steps {
                sh 'php --version'
                sh 'php i.php'
            }
        }

        stage('test') {
            steps {
                sh 'php hello.php'
            }
        }

        stage('Deploy - Staging') {
            steps {
                echo 'deploying to stage'
            }
        }

        stage('Sanity check') {
            steps {
                input "Does the staging environment look ok?"
            }
        }

        stage('Deploy - Production') {
            steps {
                echo 'deploying to production'
            }
        }
    }
}
