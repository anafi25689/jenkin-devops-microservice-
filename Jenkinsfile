pipeline {
    agent {
        docker {
            image 'maven:3.6.3'
            // optional: args '-v /tmp:/tmp' // لإضافة معاملات إضافية إذا لزم الأمر
        }
    }

	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin$PATH"

	}
    stages {
        stage ('Build') {
            steps {
                sh 'mvn --version' // عرض إصدار Maven
				sh 'docker version' // عرض إصدار Docker
                echo "Build"
            }
        }

        stage ('Test') {
            steps {
                echo "Test"
            }
        }

        stage ('Integration Test') {
            steps {
                echo "Integration Test"
            }
        }
    }
    post {
        always {
            echo 'I Am Fine'
        }
        success {
            echo 'I ran because I was successful'
        }
        failure {
            echo 'I ran because you failed'
        }
    }
}