pipeline {
    agent {
        label 'agent1'
    }
    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'master', description: 'Name of the branch to deploy')
    }

    stages {
        stage('Git clone') {
            steps {
            sh 'sudo rm -r js_counter-service || true && git clone https://github.com/asiamegic/js_counter-service.git -b dev'

            }
        }



        stage('Build Docker Image') {
            steps {
            sh 'cd js_counter-service && sudo docker build -t artemrafikov/artemrepo:counter-service .'
            }
        }


        stage('Deploy to Prod') {
            steps {
            sh 'docker stop counter-service && docker rm counter-service || docker run -d --name counter-service --privileged -p 80:3000 artemrafikov/artemrepo:counter-service'
            }
        }
    }
}

