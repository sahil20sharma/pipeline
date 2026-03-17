pipeline {
    agent any
    
    environment {
        name = 'ss'
        age = 0
    }
    
    parameters {
        string(name: "person", defaultValue: "ssjj oo", description: "who are you?")
        booleanParam(name: "ismale", defaultValue: "true", description: "")
        choice(name: "city", choices: ["jaipur","bombay","pune"], description: "select city")
    }

    stages {
        stage('build') {
            steps {
                echo 'build ho raha'
            }
        }
        stage('run command') {
            steps {
                sh 'date'
                sh 'pwd'
                sh '''
                date
                pwd
                '''
            }
        }
        stage('continue ?') {
            steps {
                input message: 'shpuld we continue', ok: 'yes we should'
                
            }
        }
        
        stage('variable check') {
            steps {
               sh ' echo "${BUILD_ID}" '
               sh '''
               echo "${name}"
               echo "${age}"
               echo "${person}"
               '''
            }
        }
        
    }
    post {
        always {
            echo "use of post with always"
        }
        failure {
            echo "this ran because of failure of pipeline"
        }
        success {
            echo "this ran to show that pipeline is successed"
        }
    }
}
