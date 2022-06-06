pipeline{
    agent { label 'java' }
    stages{
        
        stage('source code management'){
            steps{
                git branch: 'main', url: 'https://github.com/Akshay0570/js-e2e-express-server.git'
            }
        }
        stage('shell script'){
            steps{
              sh '''sudo apt update
npm run build
npm pack
npm test'''
            }
        }
        stage('diployer'){
            steps{
                rtNpmDeployer(
                    id: 'practice',
                    serverId: 'Jfrog',
                    repo: 'default-npm-local'
                )
            }
        }
    }
}