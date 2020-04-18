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
                script {
                    echo 'pulling...' + env.BRANCH_NAME
                    if( env.BRANCH_NAME == 'master') {
                        serverless deploy --stage prod --aws-profile prod_profile
                    } else {
                        serverless deploy --stage dev --aws-profile dev_profile
                    }
                }
            }
        }
    }
}
