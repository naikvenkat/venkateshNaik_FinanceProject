pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/naikvenkat/venkateshNaik_FinanceProject'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with venkatesh'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with venkatesh'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with venkatesh'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with venkatesh'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c000 myimg'
            }
        }   
    }
}
