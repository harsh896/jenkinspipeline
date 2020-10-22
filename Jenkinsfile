pipeline {
    agent any
    environment {
        name = "harsh"
        age  = 80
    }
    stages {
        stage('build') {
            steps {
                echo "Build Function = $BUILD_ID"
            }
        }
        stage('test') {
            steps {
                echo "Tested by $name"
            }
        }
        stage('deploy') {
            steps {
                echo "Deploy age is $age"
            }
        }
    }
}