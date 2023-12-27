pipeline {
    agent any
    environment {
        username = 'nsureshr'
    }
    parameters {
        string(name:'person', defaultValue: 'Nikhil Kshirsagar' , description: "who are you ?")
        booleanParam(name: 'isMale' , defaultValue: 'true' , description: "")
        choice(name: 'City' , choices: ["Achalpur" , "Amravati" , "Paratwada"] , description: "City Name")
        password(name: 'TEXT_PASSWORD' , defaultValue: 'SECRET' , description: "Sample Password PArameter")
    }
    stages {
        stage ("Hello world") {
            steps {
                echo "Hello world"
                sh 'echo "${username}"'
            }   
        }
        stage ("Environment Variable") {
           
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
                sh 'echo "${username}"'
            }
        }
        stage ('parameters') {
            steps {
                sh 'echo "${person}"'
            }
        }
        stage ('Continue ?') {
            input {
                message "Should we continue ?"
                ok "Yes continue."
            }
            steps {
                echo "Deploy on Prodution"
            }
        }
        stage ("Deploy to Production ") {
            steps {
                echo "Deploy to Production"
            }   
        }
    }
    post {
        always {
            echo "I will always say hello again!"
        }
        success {
            echo "I succeed"
        }
        failure {
            echo "I failed"
        }
    }
}
