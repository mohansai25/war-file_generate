
pipeline{
    agent  any
    stages{
        stage('git clone '){
            steps{
                    git credentialsId: '04276037-3801-4c45-8a6d-e0f38bcd99bd', url: 'https://github.com/mohansai25/war-file_generate.git'
            }
        }

        stage('compile'){
            steps{
                sh '''mvn clean
                        mvn package'''

            }
        }

        stage('Docker clean'){
            steps{
                sh 'pwd'
               //sh'cp hello.war /var/lib/jenkins/workspace/warfil_generate/docker_file'
                //Docker_clean()
            }
        }

        stage('Sleep to verify'){
            steps{
                wait_tocheck()
            }
        }

        stage('copy war file'){
            steps{
                sh 'pwd'
               //sh'cp hello.war /var/lib/jenkins/workspace/warfil_generate/docker_file'
                chdir()
            }
        }

   }
}

def Docker_clean(){
    echo 'docker image clean'
	sh 'docker stop Apache'
	sh 'docker rm Apache'
	sh 'docker rmi testing'
}

def wait_tocheck(){
    sleep time: 100, unit: 'MILLISECONDS'
}

def chdir(){
    dir('docker_file') {
    sh 'pwd'
    sh 'sudo cp ../target/hello.war .'
    sh 'docker build -t testing .'
    sh 'docker run -p 9090:8080 -d --name Apache testing:latest'
    }
}
