pipeline {
    agent {
        any
    }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests -s /root/.m2/settings.xml clean package' 
            }
        }
    }
}
