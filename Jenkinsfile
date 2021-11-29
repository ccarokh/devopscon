pipeline {
    agent any

    tools {
        maven "M3"
    }
    stages {
        stage('Build') {
            steps {
                println 'Cloning repository...'
                git 'https://github.com/ccarokh/devopscon'
                println 'Starting the build...'
		sh "mvn clean install -Pci"
            }
            post {
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                }
            }
        }
    }
}
