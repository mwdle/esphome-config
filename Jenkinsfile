@Library("JenkinsPipelines") _ // See https://github.com/mwdle/JenkinsPipelines

boolean disableIndexTriggers = env.BRANCH_NAME != 'main'

quadletPipeline(
    disableIndexTriggers: disableIndexTriggers,
    podmanSecretMappings: [
        [
            type: 'usernamePassword',
            credentialsId: 'ESPHome',
            podmanSecretPasswordName: 'esphome_password',
            podmanSecretUsernameName: 'esphome_username'
        ],
        [
            type: 'file',
            credentialsId: 'ESPHome secrets.yaml',
            podmanSecretFileName: 'esphome_secrets_yaml'
        ]
    ],
    additionalStagingExclusions: ['/images/']
)
