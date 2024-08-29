pipeline{
    agent{
        label  = "ec2"
    }

    environment{
        ENV  =  credentials('secret-id')
    }

    stages{

        stage('Deploy the multicontainer application'){
            steps{
                sh 'cp $ENV .env'
                sh 'docker-compose pull'
                sh 'docker-compose compose up -d'
            }
        }
    }
}
