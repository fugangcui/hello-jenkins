pipeline {
    agent { docker { image 'node:16.13.1-alpine' } }

    parameters {
        booleanParam(defaultValue: true, description: 'print env', name: 'is_print_env')

        string(name: 'build_version', defaultValue: '', description: 'build version')

    }

    stages {
        stage('build') {
            steps {
                sh 'node --version'
            }
        },
        stage('Test') {
            steps {
                // echo env.is_print_env
                script {
                    if (params.is_print_env) {
                        sh "printenv",
                        echo 'Run testing....'
                    } else {
                        echo "no execute 'sh printenv'"
                    }
                }
            }
        },
        stage('deploy to dev') {
            steps {
                script {
                    if (params.build_version != '') {
                        echo 'deploy to dev'
                    } else {
                        echo "no version specified when deploy to dev"
                    }
                }
            }
        },
        stage('deploy to staging') {
            steps {
                input: message: "Deploy To Staging"
                script {
                    if (params.build_version != '') {
                        echo 'deploy to staging'
                    } else {
                        echo "no version specified when deploy to staging"
                    }
                }
            }
        }
    }
}