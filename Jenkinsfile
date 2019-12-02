pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                sh 'docker create -ti --name httpd -p 8889:80 httpd'
                sh 'docker cp ${PWD}/httpd.conf httpd:/usr/local/apache2/conf/httpd.conf'
                sh 'docker start httpd'
            }
            post {
                always {
                    sh 'echo "Test post"'
                    // sh 'docker rm -f httpd'
                }
            }
        }
    }
}