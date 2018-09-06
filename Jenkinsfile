pipeline{
    agent  any
    stages{
        stage('compile'){
            steps{
                sh '''mvn clean
                        mvn package'''

            }
        }
    }
}