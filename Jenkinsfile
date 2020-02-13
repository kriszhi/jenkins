pipeline {
   agent any
   parameters {
        string(name: 'BRANCH', defaultValue: 'hotfix/r123')
        //choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        //choice choices: ['release/19R2_2','hotfix/19R2_1_1','release/19R2_1','release/19R2_0_0','release/19R1_1_0'], description: '', name: 'BRANCH'
        //extendedChoice description: '', multiSelectDelimiter: ',', name: 'BRANCH', propertyFile: '/var/lib/jenkins/git-branches/cm/release-branch-list-new.txt', propertyKey: 'branch', quoteValue: false, saveJSONParameterToFile: false, type: 'PT_SINGLE_SELECT', visibleItemCount: 1000)
    }
    triggers {
        pollSCM 'H/2 * * * *'
    }
    stages {
      stage('Build') {
         steps {
            checkout([$class: 'GitSCM', branches: [[name: "${BRANCH}"]], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/kriszhi/jenkins.git']]])
            // Get some code from a GitHub repository
            //git 'https://github.com/kriszhi/jenkins.git'

        }

      }
        
   }
}
