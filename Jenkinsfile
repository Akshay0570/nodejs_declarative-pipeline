pipeline{
    agent { label 'java' }
    stages{
        
        stage('source code management'){
            steps{
                git branch: 'main', url: 'https://github.com/Akshay0570/js-e2e-express-server.git'
            }
        }
        stage('npm run,test and pack'){
            steps{
                rtNpmInstall(
                    tool: 'nodejsv10.19.0'
                )
            }
        }
        stage('diployer'){
            steps{
                rtNpmDeployer(
                    id: practice
                    serverId: Jfrog
                    repo: default-npm-local
                )
            }
        }


       
    }
}