pipeline{
    agent any

    stages{
        stage('scm') {
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '**']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '6a03d2fd-0e0a-4ec4-a0c2-fd5e00b29fec', url: 'https://github.com/ranjanjyotidas/http-endpoint.git']]])
            }
        }
        stage('Build'){
            steps{
                echo 'pulling...' + env.BRANCH_NAME
            }
        }
    }
}