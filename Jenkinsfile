quadletPipeline(
    podmanSecretMappings: [
        [
            type: 'usernamePassword',
            credentialsId: 'ESPHome',
            podmanSecretPasswordName: 'esphome_password',
            podmanSecretUsernameName: 'esphome_username'
        ],
        [
            type: 'file',
            credentialsId: 'esphome-secrets.yaml',
            podmanSecretFileName: 'esphome_secrets_yaml'
        ]
    ],
    additionalStagingExclusions: ['/images/']
)
