pipeline{
    agent  any
    stages{
        stage('git'){
            steps{
               git credentialsId: '17aa7022-160e-47f5-9ea7-dd21a99bb9fd', url: 'https://github.com/mohansai25/war-file_generate.git'

            }

        }
        stage('compile'){
            steps{
                sh '''mvn clean
                        mvn package'''

            }

        }
    }
}