pipeline {
    parameters {
        string(name: 'DEPLOYMENT_SERVER', description: 'Target deployment server', defaultValue: 'default-server')
    }
    
    agent any
    
    stages {
        stage('Install dependencies') {
            steps {
                script {
                    def dockerTool = tool name: 'docker', type: 'org.jenkinsci.plugins.docker.commons.tools.DockerTool'
                    withEnv(["DOCKER=${dockerTool}/bin"]) {
                        sh '''
                            ${DOCKER}/docker version
                        '''
                    }
                }
            }
        }

        stage('Deployment on server') {
            steps {
                script {
                    def dockerTool = tool name: 'docker', type: 'org.jenkinsci.plugins.docker.commons.tools.DockerTool'
                    withEnv(["DOCKER=${dockerTool}/bin"]) {
                        if (params.DEPLOYMENT_SERVER == 'server1') {
                            // Connect to server1
                            sh '''
                                ${DOCKER}/docker version
                                # Add deployment steps for server1
                            '''
                        } else if (params.DEPLOYMENT_SERVER == 'server2') {
                            // Connect to server2
                            sh '''
                                ${DOCKER}/docker version
                                # Add deployment steps for server2
                            '''
                        } else {
                            echo "Invalid deployment server specified"
                        }
                    }
                }
            }
        }
    }
}
