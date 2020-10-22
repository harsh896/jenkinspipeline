pipeline {
    agent any
    triggers {
        pollSCM('')
    }
    parameters {
        choice(name: 'version', choices: ['1.1', '1.2', '1.3'], description: 'Select Version')
        string(name: 'city', defaultValue: 'Ahmedabad', description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
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
            when {
                expression {
                    params.executeTests
                }
            }
            steps {
                echo "Tested by $name"
            }
        }
        stage('deploy') {
            steps {
                echo "Deploy age is $age. City is $params.city"
            }
        }
        stage('ansible') {
            steps {
                sh '''
                echo "ansible ansible_ssh_host=192.168.33.51 ansible_ssh_user=vagrant" > hosts && \
                ansible-playbook playbook.yaml -i ca.pem
                '''
            }
        }
    }
}