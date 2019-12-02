pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                sh 'docker run -d --name httpd -v ${PWD}/httpd.conf:/usr/local/apache2/conf/httpd.conf httpd'
            }
        }
    }
}