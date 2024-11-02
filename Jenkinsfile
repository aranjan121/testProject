pipeline {
  agent any

  parameters {
    choice(
      description: 'Run flyway database migration using latest master branch from prices in what environment?',
      name: 'environments',
      choices: ['TEST','STAGE','PRE', 'PRO']
    )
  }
  environment{
	TEST_USER=credentials('TEST_USER_CRE')
  }

  stages {
    stage("Build") {
      steps {
        echo "selectedEnvironment: ${params.environments}"
        bat 'echo USER_NAME : %TEST_USER_USR%'
        bat 'echo USER_PSW : %TEST_USER_PSW%'
      }
    }
  }
}