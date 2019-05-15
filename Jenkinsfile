pipeline {
    agent {
        docker {
            image 'maven:3-alpine' 
            args '-v /root/.m2:/root/.m2:z -u root -e http_proxy=http://172.18.0.1:3128 -e https_proxy=http://172.18.0.1:3128 -e JAVA_OPTS="-Dhttp.proxyHost=192.168.0.101 -Dhttp.proxyPort=3128 -Dhttps.proxyHost=192.168.0.101 -Dhttps.proxyPort=3128"'
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}
