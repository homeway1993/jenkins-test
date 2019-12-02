pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                sh 'echo ${PWD}'
                sh 'ls ${PWD} -al'
                sh 'docker run -d --name httpd -v ${PWD}/httpd.conf:/usr/local/apache2/conf/httpd.conf httpd'
            }
            post {
                sh 'echo "Test post"'
                sh 'docker rm -f httpd'
            }
        }
    }
}