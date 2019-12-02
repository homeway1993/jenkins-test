pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                sh 'env'
                sh 'docker run -d --name httpd -v ${PWD}/httpd.conf:/usr/local/apache2/conf/httpd.conf httpd'
            }
            post {
                always {
                    sh 'echo "Test post"'
                    sh 'docker rm -f httpd'
                }
            }
        }
    }
}