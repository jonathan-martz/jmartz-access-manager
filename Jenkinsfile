String cron_string = BRANCH_NAME == "master" ? "0 18 * * *" : "0 18 * * *"

pipeline {
    agent any

    triggers { cron(cron_string) }

    stages {
        stage('Download Servers auth files') {
            steps {
                sh 'robo download:servers-auth-files'
            }
        }
        stage('Update Servers auth files') {
            steps {
                sh 'robo update:servers-auth-files'
            }
        }
    }
}
