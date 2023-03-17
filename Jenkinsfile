pipeline{
    //Directives
    agent any
    tools {
        maven 'Maven'
    }

    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }
        //stage 3: Publish artifacts to Nexus
        stage ('Publish to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.5.war', type: 'war']], credentialsId: '23f63dca-98c8-4b6d-a163-c4c318bb2490', groupId: 'com.vinaysdevopslab', nexusUrl: '172.20.10.13:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'SajjanDevopsLabs-Snapshot', version: '0.0.5'
            }
        }
        
        //stage 4: Deploying
        stage ('Deploy'){
            steps {
                echo 'deploying...'
            }
        }
    }
}


