@Library("JenkinsPipelines") _ // See https://github.com/mwdle/JenkinsPipelines

boolean disableIndexTriggers = env.BRANCH_NAME != 'main'

dockerComposePipeline(
    disableIndexTriggers: disableIndexTriggers,
    envFileCredentialIds: ["common.env", "ESPHomeConfig.env"],
    persistentWorkspace: "${env.DOCKER_VOLUMES}/deployments",
    postCheckoutSteps: {
        stage('Inject ESPHome Secrets') {
            withCredentials([file(credentialsId: 'ESPHome secrets.yaml', variable: 'SECRETS_FILE')]) {
                sh '''
                    cp "$SECRETS_FILE" config/secrets.yaml
                    chmod 600 config/secrets.yaml
                '''
            }
        }
    }
)
