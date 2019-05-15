pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') { 
            steps {
                sh '/var/jenkins_home/apache-maven-3.6.1/bin/mvn -B -DskipTests clean package' 
            }
        }
        stage('Test') { 
            steps {
                sh '/var/jenkins_home/apache-maven-3.6.1/bin/mvn test' 
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml' 
                }
            }
        }
        stage('Deliver') { 
            steps {
                sh './jenkins/scripts/deliver.sh' 
            }
        }
    }
}
