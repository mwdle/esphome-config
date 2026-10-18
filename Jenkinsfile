@Library("JenkinsPipelines") _ // See https://github.com/mwdle/JenkinsPipelines

boolean disableIndexTriggers = env.BRANCH_NAME != 'main'

quadletPipeline(
    disableIndexTriggers: disableIndexTriggers,
    podmanSecretMappings: [
        [
            type: 'usernamePassword',
            credentialsId: 'ESPHome',
            podmanSecretUsernameName: 'esphome_username',
            podmanSecretPasswordName: 'esphome_password'
        ],
        [
            type: 'file',
            credentialsId: 'ESPHome secrets.yaml',
            podmanSecretFileName: 'esphome_secrets_yaml'
        ]
    ],
    stagingExclusions: ['/images/', 'Jenkinsfile', 'LICENSE', 'README.md', 'renovate.json']
)
