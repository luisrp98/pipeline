pipeline {
    agent {
        docker { image 'node:16.13.1-alpine' }
    }
    stages {
        stage('Test') {
            steps {
                echo "Hola mundo, soy la rama main!"
                dockerBuildAndPublish {
                    repositoryName('practicas1lrp/rama_main')
                    tag('${GIT_REVISION,length=7}')
                    registryCredentials('docker-hub')
                    forcePull(false)
                    createFingerprints(false)
                    skipDecorate()
                }
            }
        }
    }
}
